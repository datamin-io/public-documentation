# Running and scheduling workflows

Datamin’s workflows can be triggered in 5 different ways:

### Manually on-demand

<figure><img src="../.gitbook/assets/Screenshot 2022-09-16 at 18.41.11.png" alt=""><figcaption></figcaption></figure>

Both buttons to schedule or run workflow manually are located in the top right corner of the workflow's canvas.&#x20;

Manual trigger is typical for:

* Test workflows, that are used for debugging or testing data sources or destinations
* Workflows that don't have any periodical schedule, but need to be run sometimes when a user needs it

After clicking on `Run workflow` button a user gets an output that shows the status of every task:

<figure><img src="../.gitbook/assets/Screenshot 2022-09-16 at 18.45.18.png" alt=""><figcaption></figcaption></figure>

### Automatically by a schedule

Scheduling is the most common way of triggering workflows. It can be configured using either a visual interface or if you are familiar with a cronjob format, you can also use this one.

<figure><img src="../.gitbook/assets/Screenshot 2022-09-16 at 18.55.53.png" alt=""><figcaption></figcaption></figure>

### From a metric when its value matches a condition

In each [metric](broken-reference), you can define which workflows to execute depending on the value of your metric:

<figure><img src="../.gitbook/assets/Screenshot 2023-01-15 at 22.14.06.png" alt=""><figcaption></figcaption></figure>

Some of the more detailed examples of metrics can be found here in the list of our use cases. Our [library of templates](library-of-templates.md) also contains multiple ones, which you can use for configuring your own metrics.

### Automatically via API as a webhook.&#x20;

For example, by Apache Airflow, Jenkins, or any other software that is already used in your company for workflow or pipeline orchestration.

More information about triggering workflows via API can be found in the [OAuth Clients](../api/oauth-clients.md) and [API Endpoints](../api/api-endpoints.md).

### In real-time from Kafka

When placed as a first task in a workflow, **external\_trigger** allows you to trigger workflows from your data streaming platforms to make it 100% real-time.

<figure><img src="../.gitbook/assets/Screenshot 2022-11-28 at 18.09.50.png" alt=""><figcaption></figcaption></figure>

The first data streaming platform we integrate with is **Kafka**. And the open-source library that can trigger workflows from it is hosted on our Github:  [https://github.com/datamin-io/kafka-trigger](https://github.com/datamin-io/kafka-trigger)

### In real-time from Google Cloud Pub/Sub

Triggering Datamin's workflow from Google Cloud Pub/Sub is as easy as just triggering it via API.

You need to create an [OAuth Client](../api/oauth-clients.md), and then use it together with the client ID and client secret in the Endpoint URL field of the subscription form of the Cloud Pub/Sub.

\
\[GET/POST] https://api.datamin.io/v1/oauth/token?client\_id=%%CLIENT\_ID%%\&client\_secret=%%CLIENT\_SECRET%%\&grant\_type=client\_credentials

<figure><img src="../.gitbook/assets/Screenshot 2023-06-12 at 23.04.06.png" alt=""><figcaption></figcaption></figure>
