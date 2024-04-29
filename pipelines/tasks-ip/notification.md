# Notification

The "**Notification**" is typically used at the end of the pipeline and doesn't have an output that can call the next task.

It is typically used to send messages to the "write" [integrations](broken-reference) you configured before.

For example, that's how you can send a message to Slack:

<figure><img src="../../.gitbook/assets/Screenshot 2023-01-09 at 17.54.19.png" alt=""><figcaption></figcaption></figure>

Resulting message in Slack:

<figure><img src="../../.gitbook/assets/Screenshot 2023-01-09 at 17.54.50.png" alt=""><figcaption></figcaption></figure>

Learn more about the [formatting of messages here](../formatting-of-messages.md).

{% hint style="info" %}
If an integration supports sending files to it (for example, [E-mails](../../integrations/library-of-integrations/e-mail.md)), you can do it the same way it is done with the "[API call](api-call.md)".
{% endhint %}

