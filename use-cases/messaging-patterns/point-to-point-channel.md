# Point-to-Point Channel

In a **Point-to-Point** messaging model, the message sender sends a message to a specific receiver, and only that receiver receives the message.

Meaning, that you have a specific message producer, that delivers this message to a specific Ylem's pipeline by calling its [API Endpoint](../../api/api-endpoints.md#run-pipeline). This can be set up by either using one of our integration libraries ([Apache Kafka](../../integrations/library-of-integrations/apache-kafka.md), [RabbitMQ](../../integrations/library-of-integrations/rabbitmq.md), [AWS Lambda](../../integrations/library-of-integrations/aws-lambda.md), [Google Pub/Sub](publish-subscribe-channel.md)) or by calling an [API Endpoint](../../api/api-endpoints.md#run-pipeline) directly from your software.

The pipeline itself needs to begin with the "[External trigger](../../pipelines/tasks-ip/external-trigger.md)" task and the rest of it depends on what you want to do with the data coming to it from the message producer.

For example, this simple pipeline receives data in real-time from an external producer and streams items to a REST API one by one.

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-01 at 10.26.21.png" alt=""><figcaption></figcaption></figure>
