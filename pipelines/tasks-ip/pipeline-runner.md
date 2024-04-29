# Pipeline runner

The "**Run pipeline**" task is designed for running pipelines from each other and transferring datasets between them.

It allows you to have smaller and simpler pipelines and reuse them by calling from other ones.&#x20;

It is a similar concept to the software engineering approach to separate monolithic products into small microservices.

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 14.52.47.png" alt=""><figcaption><p>An example of the pipeline that accepts a dataset from Apache Kafka, splits it into two subsets by filtering, and transfers each subset to a separate pipeline</p></figcaption></figure>
