# Processor

The "**Processor**" is a powerful task designed to process and transform data from the input format to a completely different output format without using any programming.

To do that it uses the power of [jq](https://jqlang.github.io/jq/) JSON processor.

Let's imagine, we have an input dataset of elements, each of which has 3 fields: `id`, `amount` and `currency`. What we want to do with it is to calculate a total amount, a total amount in euros, and get all IDs as a separate list. Something like that:

```json
{
    IDs: [1, 2, 3, 4],
    totalAmount: 1500,
    totalAmountInEUR: 1000,
}
```

That is how can be done just using "**Processor**":

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 20.04.48 (1).png" alt=""><figcaption></figcaption></figure>

More information and examples are in the [official jq documentation](https://jqlang.github.io/jq/manual/).&#x20;
