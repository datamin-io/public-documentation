# For each

"**For Each"** is a simple task that doesn't need any additional configuration. If it receives an array as input, it splits it into separate items and runs the task(s) that follow, for each of these items separately.

Such an approach helps avoid repeating tasks and simplifies pipelines.

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 14.43.09.png" alt=""><figcaption><p>Example of the pipeline that accepts streaming input from Apache Kafka, checks that it is not empty and process every item separately</p></figcaption></figure>
