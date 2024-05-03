# Message Router

A **Message Router** is software, which consumes a Message from one Message Channel and republishes it to a different Message Channel channel depending on a set of conditions.

With Datamin this pattern can be implemented by using "**Condition**" and "**Run pipeline**" tasks in the pipeline that acts as a receiver of external messages.

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-03 at 21.36.24.png" alt=""><figcaption></figcaption></figure>

This pattern implementation can in some scenarios look similar to the [Publish-Subscribe Channel](publish-subscribe-channel.md) implementation.
