# Message Dispatcher

A **Message Dispatcher** is a pattern that represents a single channel that consumes external messages and distributes them to pipelines or other performers.

The benefit of using this pattern is that you don't need to duplicate logic and all messages of a certain type will always go through the same channel before reaching the performers.

In the example below, an external message coming to this pipeline from outside of Datamin is being used for [calling an API](../../pipelines/tasks-ip/api-call.md), performing a [database query](../../pipelines/tasks-ip/query.md), and [sending a notification](../../pipelines/tasks-ip/notification.md) message. One pipeline, one message, three tasks.

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-03 at 21.43.16 (1).png" alt=""><figcaption></figcaption></figure>
