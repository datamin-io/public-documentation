# Message Filter

The **Message Filter** is a pattern used to eliminate undesired messages from a channel based on a set of criteria.

In Ylem pipelines it can be implemented by checking these criteria in the "[Condition](../../pipelines/tasks-ip/condition.md)" block. For example, in the pipeline below, it checks the criteria and process message if it matches or sends a notification alert to responsive engineers if it doesn't.

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-03 at 23.29.34.png" alt=""><figcaption></figcaption></figure>
