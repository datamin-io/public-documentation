# Datatype Channel

The **Datatype Channel** for each data type is a pattern that makes sure that a certain data consumer receives messages of a certain type.

In theory, this pattern can be implemented with Ylem, using the same approach that is used for [Message Router](message-router.md).

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-03 at 21.36.24.png" alt=""><figcaption></figcaption></figure>

However, this is what we don't recommend in case you have many different data types. If you have various data message types, there is no need to create one pipeline that accepts messages and distributes them because at some point it can grow too much a might become an unmaintainable bottleneck.

Instead, we recommend you use the [API Endpoint to trigger pipelines](../../api/api-endpoints.md) and trigger pipelines directly. One pipeline for each data type.
