# Task processing architecture

Datamin uses Apache Kafka topics for exchanging pipeline task messages while processing them. Several services are connected to it to produce messages on the topics or consume messages from it.

The high-level architecture looks like this:

<figure><img src="../.gitbook/assets/Ylem. Streaming architecture.png" alt=""><figcaption><p>Pipeline task processing architecture</p></figcaption></figure>

The processing cycle for every task consists of 10 steps:

### Step 1

The service **ylem\_pipelines\_schedule\_generator** (`./backend/pipelines`) reads pipeline schedules for the next 48 hours, prepares scheduled runs, and adds the ones that are not yet planned to run to the database table `pipelines.scheduled_runs`.&#x20;

This service is unaware of Apache Kafka and only works with the database.

### Steps 2-3

When the time comes to run pipelines the next service **ylem\_pipelines\_schedule\_publisher** (`./backend/pipelines`) reads schedules from the table `pipelines.scheduled_runs`, defines initial task(s) for each pipeline, and sends these tasks to the Kafka-topic `task_runs`.

{% hint style="info" %}
These 3 steps are only valid for the pipelines run by schedule. In all the other cases such as manual run, API-call run, external trigger, etc, the initial task(s) get published directly to the Kafka-topic `task_runs`.&#x20;

Read more about various ways to trigger pipelines [here](../pipelines/running-and-scheduling-workflows.md).
{% endhint %}

### Steps 4-5

`ylem_loadbalancer` is a service that reads tasks from the topic `task_runs` and defines the partition it needs to be sent to for the most effective processing. The most effective in this case is less loaded at the moment.&#x20;

This service is connected to the statistics of the previous runs of each pipeline and therefore it knows which pipeline is expected to be "slow" and which is most likely not. 60% of partitions are typically reserved for the "slow" pipelines and 40% for the fast ones. The decision on which partition will run the task is taken by`ylem_loadbalancer` at these two steps.

When the partition is defined, `ylem_loadbalancer` forwards the task further to the next topic `task_runs_load_balanced` for the actual processing.

### Steps 6-7

`ylem_taskrunner` is the service that does the actual processing of the task. In step 6, it reads them from the `task_runs_load_balanced` topic, processes it, and sends the result to 3 other topics:

* `task_run_results`
* `query_task_run_results`
* `notification_task_run_results`

The last 2 topics contain additional information about the results of the tasks [Query](../pipelines/tasks-ip/query.md) and [Notification](../pipelines/tasks-ip/notification.md). Currently, it can be only used for logging and debugging purposes.

### Steps 8-9

The next service `ylem_pipelines_trigger_listener` listens for the task run results in the `task_run_results` topic.&#x20;

For each new result, it checks whether the task ran successfully and if there's any task to be triggered next it sends it to the `task_runs` topic again with the output of the previous task as an input for the next one.

### Step 10

`ylem_pipelines_trigger_listener` is not the only service that listens to the `task_run_results`  topic.&#x20;

At the same time, it is being listened to by `ylem_statistics_refult_listener` which saves the result to its own Clickhouse database from where it is being served to the UI dashboard, [statistics](../statistics-and-profiling/statistics-of-runs.md), or [profiling logs](../statistics-and-profiling/slow-tasks.md).
