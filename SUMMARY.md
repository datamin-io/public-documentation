# Table of contents

## 🗒️ General information

* [Introduction to Datamin](README.md)
* [Quick start guide](general-information/quick-start-guide.md)
* [Release notes](general-information/release-notes.md)

## 💡 Integrations

* [Connecting an integration](integrations/connecting-a-data-source.md)
* [Library of integrations](integrations/library-of-integrations/README.md)
  * [Amazon Redshift](integrations/library-of-integrations/amazon-redshift.md)
  * [Apache Kafka](integrations/library-of-integrations/apache-kafka.md)
  * [APIs](integrations/library-of-integrations/apis.md)
  * [Atlassian Jira](integrations/library-of-integrations/atlassian-jira.md)
  * [AWS Lambda](integrations/library-of-integrations/aws-lambda.md)
  * [AWS RDS](integrations/library-of-integrations/aws-rds.md)
  * [AWS S3](integrations/library-of-integrations/aws-s3.md)
  * [ClickHouse](integrations/library-of-integrations/clickhouse.md)
  * [ElasticSearch](integrations/library-of-integrations/elasticsearch.md)
  * [E-mail](integrations/library-of-integrations/e-mail.md)
  * [Google Big Query](integrations/library-of-integrations/google-big-query.md)
  * [Google Cloud SQL](integrations/library-of-integrations/google-cloud-sql.md)
  * [Google Pub/Sub](integrations/library-of-integrations/google-pub-sub.md)
  * [Google Sheets](integrations/library-of-integrations/google-sheets.md)
  * [Immuta](integrations/library-of-integrations/immuta.md)
  * [Incident.io](integrations/library-of-integrations/incident.io.md)
  * [Jenkins](integrations/library-of-integrations/jenkins.md)
  * [Hubspot](integrations/library-of-integrations/hubspot.md)
  * [Microsoft Azure SQL](integrations/library-of-integrations/microsoft-azure-sql.md)
  * [MySQL](integrations/library-of-integrations/mysql.md)
  * [Opsgenie](integrations/library-of-integrations/opsgenie.md)
  * [PostgreSQL](integrations/library-of-integrations/postgresql.md)
  * [PlanetScale](integrations/library-of-integrations/planetscale.md)
  * [RabbitMQ](integrations/library-of-integrations/rabbitmq.md)
  * [Salesforce](integrations/library-of-integrations/salesforce.md)
  * [Slack](integrations/library-of-integrations/slack.md)
  * [Snowflake](integrations/library-of-integrations/snowflake.md)
  * [Tableau](integrations/library-of-integrations/tableau.md)
* [Trial data source](integrations/trial-data-source.md)

## 🚡 Pipelines

* [Pipeline management](pipelines/pipeline-management.md)
* [Tasks](pipelines/tasks-ip/README.md)
  * [Aggregator](pipelines/tasks-ip/aggregator.md)
  * [API Call](pipelines/tasks-ip/api-call.md)
  * [Code](pipelines/tasks-ip/code.md)
  * [Condition](pipelines/tasks-ip/condition.md)
  * [External trigger](pipelines/tasks-ip/external-trigger.md)
  * [Filter](pipelines/tasks-ip/filter.md)
  * [For each](pipelines/tasks-ip/for-each.md)
  * [Merge](pipelines/tasks-ip/merge.md)
  * [Notification](pipelines/tasks-ip/notification.md)
  * [Query](pipelines/tasks-ip/query.md)
  * [Pipeline runner](pipelines/tasks-ip/pipeline-runner.md)
  * [Processor](pipelines/tasks-ip/processor.md)
  * [Transformer](pipelines/tasks-ip/transformers.md)
* [Running and scheduling pipelines](pipelines/running-and-scheduling-workflows.md)
* [Library of templates](pipelines/library-of-templates.md)
* [Environment variables](pipelines/environment-variables.md)
* [Mathematical functions and operations](pipelines/mathematical-functions.md)
* [Formatting of messages](pipelines/formatting-of-messages.md)

## 📈 Statistics and profiling

* [Statistics of runs](statistics-and-profiling/statistics-of-runs.md)
* [Slow tasks](statistics-and-profiling/slow-tasks.md)

## 📊 Metrics

* [Metric management](metrics/metric-management.md)
* [Using previous values of a metric](metrics/using-the-average-value-of-a-metric.md)

## 💼 Use cases, patterns, templates, examples <a href="#use-cases" id="use-cases"></a>

* [Use cases](use-cases/use-cases.-homepage.md)
* [Messaging patterns](use-cases/messaging-patterns/README.md)
  * [Datatype Channel](use-cases/messaging-patterns/datatype-channel.md)
  * [Message Dispatcher](use-cases/messaging-patterns/message-dispatcher.md)
  * [Messaging Bridge](use-cases/messaging-patterns/messaging-bridge.md)
  * [Message Bus](use-cases/messaging-patterns/message-bus.md)
  * [Message Filter](use-cases/messaging-patterns/message-filter.md)
  * [Message Router](use-cases/messaging-patterns/message-router.md)
  * [Point-to-Point Channel](use-cases/messaging-patterns/point-to-point-channel.md)
  * [Publish-Subscribe Channel](use-cases/messaging-patterns/publish-subscribe-channel.md)
  * [Pull-Push](use-cases/messaging-patterns/pull-push.md)
* [Functional use cases](use-cases/functional-use-cases/README.md)
  * [Streaming from Apache Kafka and messaging queues](use-cases/functional-use-cases/streaming-from-apache-kafka-and-messaging-queues.md)
  * [Streaming from APIs](use-cases/functional-use-cases/streaming-from-apis.md)
  * [Streaming from databases](use-cases/functional-use-cases/streaming-from-databases.md)
  * [Data orchestration, transformation and processing](use-cases/functional-use-cases/data-orchestration-transformation-and-processing.md)
  * [Usage of Python and Pandas](use-cases/functional-use-cases/usage-of-python-and-pandas.md)
  * [KPI Monitoring](use-cases/functional-use-cases/kpi-monitoring.md)
  * [OKRs and custom metrics](use-cases/functional-use-cases/okrs-and-custom-metrics.md)
  * [Data Issues & Incidents](use-cases/functional-use-cases/data-issue-monitoring.md)
  * [Reporting](use-cases/functional-use-cases/reporting.md)
  * [Other functional use cases](use-cases/functional-use-cases/other-functional-use-cases.md)
* [Industry-specific use cases](use-cases/industry-specific-use-cases/README.md)
  * [Finance and Payments](use-cases/industry-specific-use-cases/finance-and-payments.md)
  * [E-commerce & Logistics](use-cases/industry-specific-use-cases/e-commerce.md)
  * [Customer Success](use-cases/industry-specific-use-cases/customer-success.md)
  * [Security, Risk, and Anti-Fraud](use-cases/industry-specific-use-cases/security-risk-aml-and-fraud.md)
  * [Anti-Money Laundering (AML)](use-cases/industry-specific-use-cases/anti-money-laundering-aml.md)

## 🔌 API

* [OAuth clients](api/oauth-clients.md)
* [API Reference](api/api-endpoints.md)

## 👁️‍🗨️ Other resources

* [FAQ](other-resources/faq.md)
* [Our blog on Medium](https://medium.com/datamin)
