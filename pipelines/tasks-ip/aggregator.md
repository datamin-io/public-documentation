# Aggregator

The "**Aggregator"** is designed to transform an input dataset into one single variable.

To do that it can use [mathematical functions](../mathematical-functions.md) like `SUM()`, `AVG()` and other aggregating functions and operations like `+`,`-`,`==`, `!=`,`<`,`>`. etc. The full list can be found [here](../mathematical-functions.md#arithmetical-and-logical-operations)

In addition to the mathematical expression, you can also configure how you want the output variable to be called to access it in the next task.

In the following example, an aggregator calculates an average invoice amount in the input dataset and rounds it down to 2-digit precision. The result is available in the next task as `{{ average_amount }}`

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 19.59.22.png" alt=""><figcaption></figcaption></figure>
