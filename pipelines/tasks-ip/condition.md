# Condition

The "**Condition"** is a one-of-a-kind task having two outputs instead of one.

It allows you to branch your pipelines and dynamically execute one part of it if the condition result is true and another one if it is false.

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 21.23.50.png" alt=""><figcaption></figcaption></figure>

As same as the "[Aggregator](aggregator.md)" the "**Condition**" can use [mathematical functions](../mathematical-functions.md) like `SUM()`, `AVG()` and other aggregating functions and operations like `+`,`-`,`==`, `!=`,`<`,`>`. etc. The full list can be found [here](../mathematical-functions.md#arithmetical-and-logical-operations).&#x20;

The result of it can be compared with a desired value.

For example:

<div align="center" data-full-width="false">

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 21.26.23.png" alt=""><figcaption><p>If list is not empty</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 21.26.48.png" alt=""><figcaption><p>If average amount is equal to the last amount</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 21.27.15.png" alt=""><figcaption><p>Or even a single field value can be used</p></figcaption></figure>

</div>

In addition to that, you can execute several tasks depending on the condition is true or false:

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 21.30.44.png" alt=""><figcaption></figcaption></figure>

Or build more complicated branched and nested conditions:

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 21.32.22.png" alt=""><figcaption></figcaption></figure>
