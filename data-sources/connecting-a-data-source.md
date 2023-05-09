# Connecting a data source

## Types of Data Sources

### SQL-based ones

On the [data source](https://app.datamin.io/data-sources) page, you can configure your data sources to be used in workflows. It can be your production database replica, your data warehouse, staging or testing database, or any other storage.

{% hint style="info" %}
We recommend having both production and testing data sources connected, so you can always properly test your workflows before using them on production.
{% endhint %}

At the moment we support a wide range of **SQL-based** data sources, such as&#x20;

* **MySQL**,&#x20;
* **Snowflake**,&#x20;
* **Postgres**,&#x20;
* **Google Big Query**,&#x20;
* **AWS RDS**,
* **Amazon Redshift**&#x20;
* **Immuta**
* **Planetscale**
* **ClickHouse**
* **ElasticSearch**
* and others.&#x20;

And this list is growing since we are adding new ones.

Connecting an SQL-based data source is easy. You just need to create us a read-only user, give it the necessary permissions, and don't forget to add an additional security layer such as SSH tunnel or/and enabling connections from our IP, which you can find in the data source form.

<figure><img src="../.gitbook/assets/Screenshot 2022-09-14 at 22.44.13.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-09-14 at 22.43.16.png" alt=""><figcaption></figcaption></figure>

### API-based data sources

On top of that, Datamin also supports JSON APIs as data sources. Any API which returns JSON data can be used as a data source, such as typically:

* **Salesforce**
* **Hubspot**
* **Your own backend APIs**
* etc.

In this case, instead of using a [Query](../workflows/tasks-ip/#query) task start your workflow with an [API\_Call](../workflows/tasks-ip/#api-call) task and the rest stays the same.

### Data streaming platforms as data sources

The unique feature of **Datamin** that makes us 100% real-time is an integration with **Kafka** as a data source. It allows you to trigger workflows in a real-time right after getting a new message from **Kafka** topic.

In order to do it, you need to make two steps:

1. Install and configure our [open-source kafka-trigger library](https://github.com/datamin-io/kafka-trigger). A detailed description of how to do it is in its README.
2. Create a workflow you want to trigger, starting with the [External\_trigger](../workflows/tasks-ip/#external-trigger) task.

<figure><img src="../.gitbook/assets/Screenshot 2022-11-28 at 18.09.50.png" alt=""><figcaption></figcaption></figure>





