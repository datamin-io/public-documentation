# Merge

"**Merge"** is a task that is used when you have two or more datasets coming from different sources and want to merge them into one dataset.

These are the possible resulting options for the merge:

* If two rows have the same values in all fields enumerated in this parameter, they will be merged.
  * If you add a field "id" — the block will merge rows with the same IDs,&#x20;
  * If you add fields "id" and "name" — rows with the same ID and name will be merged.
* If you leave key field names empty, all rows from all datasets will be merged.&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 20.34.23.png" alt=""><figcaption></figcaption></figure>

In the following examples, items with the same `id` and `type` will be merged into one:

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 20.34.00.png" alt=""><figcaption></figcaption></figure>
