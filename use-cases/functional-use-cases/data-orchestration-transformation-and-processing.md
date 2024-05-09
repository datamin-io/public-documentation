# Data orchestration, transformation and processing

Not only can you stream data from one place to another using Datamin, but also fully orchestrate the process and do the entire data transformation and processing.

Everything that is happening in pipelines between the retrieval of data to sending it outside of Datamin can be orchestrated by the set of the following pipeline tasks:

* **"**[**Aggregator**](../../pipelines/tasks-ip/aggregator.md)**"** is designed to transform an input dataset into one single variable. To do that it uses [mathematical functions](../../pipelines/mathematical-functions.md) like `SUM()`, `AVG()` and other aggregating functions.
* **"**[**Code**](../../pipelines/tasks-ip/code.md)**"** is a task that allows you to use Python and Pandas framework for complex logic.
* **"**[**Condition**](../../pipelines/tasks-ip/condition.md)**"** allows you to branch your pipelines and dynamically execute one part of it if the condition result is true and another one if it is false.
* **"**[**Filter**](../../pipelines/tasks-ip/filter.md)**"** is responsible for the basic filtering of datasets by a certain value of a certain key.
* "[**For Each**](../../pipelines/tasks-ip/for-each.md)**"** allows running the next task for each of input items separately.
* **"**[**Merge**](../../pipelines/tasks-ip/merge.md)**"** merges data coming to the pipeline from two or more data sources.
* **"**[**Processor**](../../pipelines/tasks-ip/processor.md)**"** is a task that allows you to transform, filter, and map data using the functionality of the JQ library.
* "[**Transformer**](../../pipelines/tasks-ip/transformers.md)**"** converts data in different formats or extracts values.

These tasks make our pipelines very agile and equip you with versatile flexibility of how to orchestrate your data. And a combination of them is only limited by your creativity.

## Tasks and human language

Even more interesting, our pipeline tasks are designed in a way so that you can easily describe the entire functionality of the pipeline with one sentence.

For example,&#x20;

### Task

**Merge** data from two databases, check if the resulting dataset meets **conditions**, **filter** it if yes, and process **each** of the items in the resulting dataset.

### Implementation

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-09 at 23.51.06.png" alt=""><figcaption></figcaption></figure>

Such an intuitive conversion from human language to pipelines simplifies the communication between stakeholders and data engineers significantly and also:

* Establishes a common vocabulary
* Reduces time on explanations
* Accelerates implementation
* Minimizes errors
