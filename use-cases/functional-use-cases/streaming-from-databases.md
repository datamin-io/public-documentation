# Streaming from databases

For streaming data from databases, you need to read data in your pipeline with the "[Query](../../pipelines/tasks-ip/query.md)" task:



<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 20.21.36.png" alt=""><figcaption></figcaption></figure>

When the pipeline is triggered, this task will make an SQL query to the database, you have configured in your integration and use the response data for the entire pipeline.

We support a wide range of SQL integrations to read from and write data to. You can find more information on how to configure such integrations on their specific pages:

* [PostgreSQL](../../integrations/library-of-integrations/postgresql.md)
* [Snowflake](../../integrations/library-of-integrations/snowflake.md)
* [MySQL](../../integrations/library-of-integrations/mysql.md)
* [AWS RDS](../../integrations/library-of-integrations/aws-rds.md)
* [Google Big Query](../../integrations/library-of-integrations/google-big-query.md)
* [Google Cloud SQL](../../integrations/library-of-integrations/google-cloud-sql.md)
* [ClickHouse](../../integrations/library-of-integrations/clickhouse.md)
* [Immuta](../../integrations/library-of-integrations/immuta.md)
* [ElasticSearch](../../integrations/library-of-integrations/elasticsearch.md)
* [PlanetScale](../../integrations/library-of-integrations/planetscale.md)

&#x20;Some examples of the streaming pipelines from the API:

## Streaming from database to API

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-09 at 20.42.09.png" alt=""><figcaption></figcaption></figure>

## Streaming from database to database

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-09 at 20.39.49.png" alt=""><figcaption></figcaption></figure>

Same as in the case of [streaming from APIs](streaming-from-apis.md), the pipelines above are just examples and your real pipelines will most probably be more complicated and will contain more transformation and processing of data:

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-09 at 20.39.04.png" alt=""><figcaption></figcaption></figure>
