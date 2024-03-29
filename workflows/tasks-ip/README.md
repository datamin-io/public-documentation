# Tasks

Workflows are built from tasks. Currently, Datamin supports the following 8 kinds of tasks:

### Query

**Queries** and **API Calls** are usually the first ones in the workflow.&#x20;

Using **Query** you can write an SQL query you want to run against your [Data Sources](../../data-sources/connecting-a-data-source.md) or use a constructor of queries if you are not familiar with SQL. Here is what the constructor of queries typically looks like:

<figure><img src="../../.gitbook/assets/Screenshot 2022-09-16 at 17.56.11.png" alt=""><figcaption></figcaption></figure>

Here we retrieve all customers, who created an account today and completed the onboarding process. Also, we sort the list from newest to oldest.

### API Call

**API Calls** can be used at the beginning of the workflow to retrieve data and also at the end to send data to a certain external or internal API.

It supports all the attributes of a normal API Call when it is done from the command line using `curl` or a software like `Postman`, such as body payload, headers, and query strings.

<figure><img src="../../.gitbook/assets/Screenshot 2022-09-16 at 18.07.05.png" alt=""><figcaption></figcaption></figure>

The result of the **Query** or **API Call** can be sent to Aggregators, Conditions, or Transformers.

### Merge

**Merge** is typically used when you have two or more data sources and want to merge data sets coming from both.&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2022-09-16 at 18.13.03.png" alt=""><figcaption></figcaption></figure>

### Aggregator

**Aggregators** help you to implement basic aggregating formulas and pre-build functions such as COUNT(), AVG(), SUM(), and other ones. They are typically used for transforming and incoming datasets into one single value.

<figure><img src="../../.gitbook/assets/Screenshot 2022-09-16 at 18.10.58.png" alt=""><figcaption></figcaption></figure>

### Condition

**Condition** is a block where you can compare input and expectations and continue with different workflow scenarios depending on if it is true or false.

<figure><img src="../../.gitbook/assets/Screenshot 2022-09-16 at 18.14.30.png" alt=""><figcaption></figcaption></figure>

### For Each

**For Each** allows running the next task for each of the items in the dataset separately. Working with this block is pretty straightforward and doesn't even require any configuration, except the name.&#x20;

### Filter

Simple filters allow you to filter your dataset by a certain value of a certain key:

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-27 at 20.37.42.png" alt=""><figcaption></figcaption></figure>

If you are looking for more advanced filtering options, let's look at what [transformers](transformers.md#extracting-and-filtering-data-with-gjson) provide.

### Transformer

**Transformers** help you to transform data into different formats or extract values.

For example, convert the dataset to CSV before sending it as an attachment to an Email.

More detailed examples of how to use transformers are described on a [separate page](transformers.md).

<figure><img src="../../.gitbook/assets/Screenshot 2022-09-16 at 18.18.58.png" alt=""><figcaption></figcaption></figure>

### Notification

In the end, you can either call APIs with **API Calls** or send notifications with **Notification** tasks to the [Destinations](../../destinations/connecting-a-destination.md) you've configured before.

<figure><img src="../../.gitbook/assets/Screenshot 2022-09-16 at 18.21.46.png" alt=""><figcaption></figcaption></figure>

### External trigger

When placed as a first task in a workflow, **external\_trigger** allows you to trigger workflows from your data streaming platforms to make it 100% real-time.

<figure><img src="../../.gitbook/assets/Screenshot 2022-11-28 at 18.09.50.png" alt=""><figcaption></figcaption></figure>

The first data streaming platform we integrate with is **Kafka**. And the open-source library that can trigger workflows from it is hosted on our Github:  [https://github.com/datamin-io/kafka-trigger](https://github.com/datamin-io/kafka-trigger)

### Run workflow

This task allows you to connect workflows to each other by running one from another one.&#x20;

The main benefit of it is in the **DRY** principle, instead of repeating the same logic in multiple workflows, it can be re-used by connecting workflows to each other as a chain.

<div>

<figure><img src="../../.gitbook/assets/Screenshot 2023-01-09 at 16.40.53.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Screenshot 2023-01-09 at 16.40.34.png" alt=""><figcaption></figcaption></figure>

</div>

### Python

As with each and every no-code solution, we still allow using some code if necessary:-)

Therefore, we developed a new special task called **Python**, which can be used for transforming data sets on the fly.

Here is an example, of how Python can help you iterate through input data, extracting from the database and transforming it on the fly. In this particular case, converting numbers into strings.

<div>

<figure><img src="../../.gitbook/assets/Screenshot 2023-02-17 at 13.54.01.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Screenshot 2023-02-17 at 13.53.48.png" alt=""><figcaption></figcaption></figure>

</div>

### GPT

From now on you can utilize the power of GPT by OpenAI as a dedicated task in workflows for transforming, cleaning, or completing your data.

<div>

<figure><img src="../../.gitbook/assets/Screenshot 2023-05-09 at 22.37.43 (1).png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Screenshot 2023-05-09 at 22.17.42.png" alt=""><figcaption></figcaption></figure>

</div>

Find more use cases on a [dedicated page](../../use-cases-examples-templates/gpt-by-openai.md).
