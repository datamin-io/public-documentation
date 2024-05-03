# Publish-Subscribe

The main difference between a [Point-to-Point](point-to-point.md) and **Publish-Subscribe** messaging model is that a message is not sent to a specific receiver but to a specific topic, and all the subscribed receivers receive the message.

If you have a specific message producer ([Apache Kafka](../../integrations/library-of-integrations/apache-kafka.md), [RabbitMQ](../../integrations/library-of-integrations/rabbitmq.md), [AWS Lambda](../../integrations/library-of-integrations/aws-lambda.md), [Google Pub/Sub](publish-subscribe.md)), that delivers this message to a specific Datamin's pipeline by calling its [API Endpoint](../../api/api-endpoints.md#run-pipeline), this pipeline acts as a topic that has a specific distribution logic responsible for forwarding the message to subscribed pipelines (receivers).

The pipeline itself needs to begin with the "[External trigger](../../pipelines/tasks-ip/external-trigger.md)" task and can contain a set of conditions that define what pipelines to forward this message to.

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-03 at 14.04.49.png" alt=""><figcaption><p>Publish-subscribe implementation using Datamin</p></figcaption></figure>

As we can see from this pipeline, there are two subscription condition checks. And how to define a condition itself is up to you. We recommend having a standard message type in your message schema that will always be present in all the messages and then the condition will check if that matches a certain value.

For example:

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-03 at 14.11.18.png" alt=""><figcaption></figcaption></figure>

Or to make it even more advanced, you can create an [environment variable](../../pipelines/environment-variables.md) for this message type, that can be reused for multiple tasks and pipelines:



<div>

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-03 at 14.12.25.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-03 at 14.12.57.png" alt=""><figcaption></figcaption></figure>

</div>

Then after the condition is checked if the first one is true, it forwards the data to "**pipeline 1**", which is subscribed to that type of message.&#x20;

If the second one is true, it forwards the message to "**pipeline 2**" and "**pipeline 3**", which is how you subscribe multiple pipelines to the same message.

As you can see this pipeline is not aware of what data the message contains and purely acts as an intermediary distributor to the subscribed pipelines that contain the logic itself. We recommend you always keep this way.
