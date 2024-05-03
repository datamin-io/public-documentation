# Messaging Bridge

Imagine that you have multiple messaging systems used in your organization. How can multiple messaging systems be connected so that messages available on one are also available on the others?

A **Messaging Bridge**, is a connection between messaging systems, to replicate messages between systems.

It is very easy to implement this pattern with Datamin. You just need to create a pipeline that begins with the "**External\_trigger**" task accepts the input message from one system and then uses the "**API\_call**" to publish the input message to the API of another system.

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-03 at 20.32.12.png" alt=""><figcaption></figcaption></figure>

It is a very simple pipeline that just forwards the message to the second messaging system. But of course, your real use case might be as complicated as you want, containing [conditions](../../pipelines/tasks-ip/condition.md), [filters](../../pipelines/tasks-ip/filter.md), [processors](../../pipelines/tasks-ip/processor.md), [transformations](../../pipelines/tasks-ip/transformers.md), and other tasks that prepare the input data to be accepted by the second messaging system.

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-03 at 20.35.43.png" alt=""><figcaption></figcaption></figure>
