---
description: >-
  Since Ylem is a real-time streaming platform, our goal is to provide you
  with a tool with which you can deliver your data from one place to another as
  fast as possible.
---

# Streaming from Apache Kafka and messaging queues

The fastest way of doing it is to stream data to Ylem directly from such software as [Apache Kafka](../../integrations/library-of-integrations/apache-kafka.md), [RabbitMQ](../../integrations/library-of-integrations/rabbitmq.md), [Google Pub/Sub](../../integrations/library-of-integrations/google-pub-sub.md), Amazon SQS, [AWS Lambda](../../integrations/library-of-integrations/aws-lambda.md), etc.

## Triggering pipeline from outside of Ylem

No matter which software you want to stream data from, you need to start your pipeline with the "[External trigger](../../pipelines/tasks-ip/external-trigger.md)" task.

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 20.27.01.png" alt=""><figcaption></figcaption></figure>

This task doesn't require any additional configuration but allows a pipeline to be triggered [through the API endpoint](../../api/api-endpoints.md#run-pipeline), which is used by all of the open-source libraries we developed for external integration.

After this task you can create any pipeline of any logic you want, using the input data that you are planning to send to Ylem from your messaging platforms.

With the following pipeline you can stream from the external messaging platforms to your API:

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-01 at 10.26.21.png" alt=""><figcaption></figcaption></figure>

Or to your database:

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-09 at 20.06.06.png" alt=""><figcaption></figcaption></figure>

## Streaming from Apache Kafka

To stream from Apache Kafka, you can use our open-source library, which triggers pipelines when a new message arrives to a topic and forwards this message as input to the pipeline:  [https://github.com/ylem-co/ylem-kafka-trigger](https://github.com/ylem-co/ylem-kafka-trigger)

* [Apache Kafka integration](../../integrations/library-of-integrations/apache-kafka.md)
* [Apache Kafka example in the intro guide](../../general-information/quick-start-guide.md#example-2.-streaming-from-apache-kafka-to-an-api)

## Streaming from RabbitMQ

RabbitMQ allows you to listen to various events in your infrastructure. At the same time, Ylem can become one of the consumers of RabbitMQ messages.

For this integration, you can use our [open-source RabbitMQ consumer](https://github.com/ylem-co/ylem-rabbitmq-consumer).

Read the detailed [documentation about how to configure it here](https://github.com/ylem-co/ylem-rabbitmq-consumer/blob/main/README.md).

## Streaming from Google Pub/Sub

Streaming from Google Pub/Sub to Ylem's pipelines does not even require any additional library. It is as easy as just triggering pipelines via API.

The procedure of how to trigger pipelines via API is described [here in our documentation](../../api/api-endpoints.md#run-pipeline) where you can also get the Endpoint URL.

* [Google Pub/Sub integration](../../integrations/library-of-integrations/google-pub-sub.md)

## Streaming from AWS Lambda

AWS Lambda allows you to listen to various events in the AWS universe. Therefore these data can immediately be streamed to Ylem by triggering our [API for pipelines](../../api/api-endpoints.md#run-pipeline).

We are building an open-source AWS Lambda function for you and it is coming live soon.

* [AWS Lambda integration](../../integrations/library-of-integrations/aws-lambda.md)

## Streaming from other messaging platforms

If you want to stream from other messaging platforms, that are not mentioned here, you can either develop an integration yourself [using our API](../../api/api-endpoints.md), or contact us and request the new integration.
