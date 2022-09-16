# Tasks

Workflows are built from tasks. Currently, Datamin supports the following 8 kinds of tasks:

<figure><img src="../.gitbook/assets/Screenshot 2022-09-16 at 17.51.15.png" alt=""><figcaption></figcaption></figure>

### Query

**Queries** and **API Calls** are usually the first ones in the workflow.&#x20;

Using **Query** you can write an SQL query you want to run against your [Data Sources](../data-sources/connecting-a-data-source.md) or use a constructor of queries if you are not familiar with SQL. Here is what the constructor of queries typically looks like:

<figure><img src="../.gitbook/assets/Screenshot 2022-09-16 at 17.56.11.png" alt=""><figcaption></figcaption></figure>

Here we retrieve all customers, who created an account today and completed the onboarding process. Also, we sort the list from newest to oldest.

### API Call

**API Calls** can be used at the beginning of the workflow to retrieve data and also at the end to send data to a certain external or internal API.

It supports all the attributes of a normal API Call when it is done from the command line using `curl` or a software like `Postman`, such as body payload, headers, and query strings.

<figure><img src="../.gitbook/assets/Screenshot 2022-09-16 at 18.07.05.png" alt=""><figcaption></figcaption></figure>

The result of the **Query** or **API Call** can be sent to Aggregators, Conditions, or Transformers.

### Merge

**Merge** is typically used when you have two or more data sources and want to merge data sets coming from both.&#x20;

<figure><img src="../.gitbook/assets/Screenshot 2022-09-16 at 18.13.03.png" alt=""><figcaption></figcaption></figure>

### Aggregator

**Aggregators** help you to implement basic aggregating formulas and pre-build functions such as COUNT(), AVG(), SUM(), and other ones. They are typically used for transforming and incoming datasets into one single value.

<figure><img src="../.gitbook/assets/Screenshot 2022-09-16 at 18.10.58.png" alt=""><figcaption></figcaption></figure>

### Condition

**Condition** is a block where you can compare input and expectations and continue with different workflow scenarios depending on if it is true or false.

<figure><img src="../.gitbook/assets/Screenshot 2022-09-16 at 18.14.30.png" alt=""><figcaption></figcaption></figure>

### For Each

**For Each** allows running the next task for each of the items in the dataset separately. Working with this block is pretty straightforward and doesn't even require any configuration, except the name.&#x20;

### Transformer

**Transformers** help you to transform data into different formats or extract values.

For example, convert the dataset to CSV before sending it as an attachment to an Email.

<figure><img src="../.gitbook/assets/Screenshot 2022-09-16 at 18.18.58.png" alt=""><figcaption></figcaption></figure>

### Notification

In the end, you can either call APIs with **API Calls** or send notifications with **Notification** tasks to the [Destinations](../destinations/connecting-a-destination.md) you've configured before.

<figure><img src="../.gitbook/assets/Screenshot 2022-09-16 at 18.21.46.png" alt=""><figcaption></figcaption></figure>
