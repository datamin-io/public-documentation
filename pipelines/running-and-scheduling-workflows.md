# Running and scheduling pipelines

Ylem’s pipelines can be triggered in 5 different ways:

### Manually on-demand

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 14.58.09.png" alt=""><figcaption></figcaption></figure>

Both buttons to schedule or run the pipeline manually are located in the top right corner of the pipeline's canvas.&#x20;

A manual trigger is typically used for:

* Testing and debugging new pipelines or pipelines that stopped working as expected
* Pipelines that don't have any periodical schedule, don't need to be triggered through the API but need to be run sometimes on demand when a user needs it

After clicking on the "**Run pipeline"** button a user gets an output that shows the status of every task or can open the full-text output log:

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 15.05.16.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 15.04.20.png" alt=""><figcaption></figcaption></figure>

### Automatically by a schedule

Scheduling is the most common way of triggering pipelines that need to do a periodical job. For example, reporting, and data preparation.

It can be configured using either a visual interface or if you are familiar with a cronjob format, you can also use this one.

<figure><img src="../.gitbook/assets/Screenshot 2022-09-16 at 18.55.53.png" alt=""><figcaption></figcaption></figure>

### Automatically via API.&#x20;

For example, by Apache Airflow, Jenkins, or any other software that is already used in your company for workflow or pipeline orchestration.

More information about triggering pipelines via API can be found in the [OAuth Clients](../api/oauth-clients.md) and [API Endpoints](../api/api-endpoints.md).

### In real-time from Apache Kafka, RabbitMQ, Google Pub/Sub, etc.

When placed as a first task in a pipeline, **external\_trigger** allows you to trigger the pipeline from your data streaming platforms to make it 100% real-time.

<figure><img src="../.gitbook/assets/Screenshot 2022-11-28 at 18.09.50.png" alt=""><figcaption></figcaption></figure>

More specific details can be found on the detailed pages for each integration:

* [Apache Kafka](../integrations/library-of-integrations/apache-kafka.md)
* [RabbitMQ](../integrations/library-of-integrations/rabbitmq.md)
* [Google Pub/Sub](../integrations/library-of-integrations/google-pub-sub.md)
* [AWS Lambda](../integrations/library-of-integrations/aws-lambda.md)

### From a metric when its value matches a condition

In each [metric](broken-reference), you can define which pipelines to execute depending on the value of your metric:

<figure><img src="../.gitbook/assets/Screenshot 2024-04-17 at 13.56.04.png" alt=""><figcaption></figcaption></figure>

Some of the more detailed examples of metrics can be found in the [list of our use cases](../use-cases/use-cases.-homepage.md). Our [library of templates](library-of-templates.md) also contains multiple ones, which you can use for configuring your metrics.
