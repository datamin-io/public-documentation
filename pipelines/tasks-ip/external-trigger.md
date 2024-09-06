# External trigger

The task "**External trigger**" needs to be placed at the very beginning of the pipeline if you want to execute it by calling [Ylem's API](../../api/api-endpoints.md#run-pipeline) from the outside.

The following cases are the most common for such a situation:

* Trigger pipeline from [Apache Kafka](../../integrations/library-of-integrations/apache-kafka.md), [AWS Lambda](../../integrations/library-of-integrations/aws-lambda.md), [AWS S3](../../integrations/library-of-integrations/aws-s3.md), [Google Pub/Sub](../../integrations/library-of-integrations/google-pub-sub.md), [RabbitMQ](../../integrations/library-of-integrations/rabbitmq.md)
* Trigger pipeline by [calling an API](../../api/api-endpoints.md#run-pipeline) directly or calling it from your custom script

The input dataset that you transfer to the API endpoint will also be available in the task that follows "**External trigger**":

The following simple pipeline example accepts data from outside and forwards it further as a notification.

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 15.00.46.png" alt=""><figcaption></figcaption></figure>

Let's send the following JSON as input to the [API endpoint](../../api/api-endpoints.md#run-pipeline) that triggers this pipeline:

```json
{
    "info": "some information",
    "customer_id": 1
}
```

As you can see the input dataset is available in the "Notification task" as a whole under the `{{ INPUT() }}` function and also every input key-value pair is available separately by its key name.

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 15.01.03.png" alt=""><figcaption></figcaption></figure>
