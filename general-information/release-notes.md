# Release notes

## Release history

Only important major releases are present in this list:

### Release 10.02.2025

* Integration with WhatsApp (through Twilio)

### Release 07.11.2024

* Open-source edition. The first beta version is on [https://github.com/ylem-co/ylem](https://github.com/ylem-co/ylem)

### Release 06.09.2024

* Datamin becomes Ylem

### Release 17.07.2024

* Dark UI theme as the default theme
* Logging and profiling for the "[Run pipeline](../pipelines/tasks-ip/pipeline-runner.md)" task
* Support of several new Python modules for the "[Code](../pipelines/tasks-ip/code.md)" task
* Pipeline canvas UI improvements

### Release 20.06.2024

* New [math functions](../pipelines/mathematical-functions.md): ABS, NEG, SIGN, INT, STRING
* Improvements in the error logging for tasks and pipelines
* Improvements in the UI for OAuth

### Release 30.05.2024

* Main dashboard improvements
* Graphs of pipeline and metric runs per month on the dashboard

### Release 19.05.2024

* Streaming from AWS S3 to Datamin's pipeline through AWS Lambda
* An open-source [AWS S3 to pipeline lambda trigger](https://github.com/datamin-io/s3-lambda-trigger).

### Release 10.05.2024

* Brand new fully reworked documentation

### Release 02.04.2024

* Pipelines instead of workflows

### Release 26.03.2024

* Insert/Update data in SQL databases with Query task

### Release 23.03.2024

* **Integrations** instead of data sources and destinations.

### Release 20.02.2024

* Performance improvements for statistics and profiling modules

### Release 22.01.2024

* New task: Processor with the functionality of [jq](https://jqlang.github.io/jq/) library
* Frontend improvements and bugfixes

### Release 19.01.2024

* Significantly improved performance, load balancing, and resource consumption of the workflow scheduler and runner

### Release 17.01.2024

* Profiling of slow queries and other tasks

### Release 14.01.2024

* Logs for metrics
* Improvements in statistics for workflows and metrics

### Release 12.01.2024

* "Pandas" Python data analytics library is available in the "Code" task
* Logs of runs for workflows

### Release 09.01.2024

* Introduction of the dark mode/light mode
* A new informative and powerful dashboard
* Searching bar for workflows, metrics, and tasks
* Performance improvements and a higher speed of resource loading

### Release 20.12.2023

* Open source library for streaming data from RabbitMQ: [https://github.com/datamin-io/datamin-rabbitmq-consumer](https://github.com/datamin-io/datamin-rabbitmq-consumer)

### Release 26.11.2023

* Better organized workflows and metric views with tabs
* Bigger and more informative forms for editing tasks
* Better code highlighting and line numbers in all the fields with SQL, Python, and Long texts
* As a preparation for introducing more programming languages in workflows, the Python task was renamed to Code

### Release 29.07.2023

* Improved visibility of historical metric values on the statistics page and in the list of metrics

### Release 23.07.2023

* New UI for workflows for better profiling and debugging

### Release 27.03.2023

* New destination: **Jenkins**. Jobs can now be triggered directly from Datamin's workflows
* Improvements in demo workflows and metrics

### Release 18.03.2023

* New functions for metrics: METRIC\_QUANTILE, METRIC\_MEDIAN.

### Release 14.03.2023

* Atlassian Opsgenie as a new destination for alerts

### Release 17.02.2023

* Adding [METRIC\_AVG](../pipelines/mathematical-functions.md) function to metrics

### Release 16.02.2023

* Introducing [Python](../pipelines/tasks-ip/) for data transformation in workflows

### Release 15.01.2023

* Sending messages in private groups in Slack

### Release 12.01.2023

* Folders and templates for metrics
* Grid/list views for metrics and workflows

### Release 09.01.2023

* Supporting **ClickHouse** as a data source

### Release 07.01.2023

* Introducing metrics and thresholds

### Release 19.12.2022

* **Amazon Redshift** as a data source

### Release: 09.12.2022

* Environment variables

### Release: 28.11.2022

* Integration of workflows with data streaming platforms as data sources: **Kafka** first.

### Release date: 26.11.2022

* Integration with **Google Spreadsheets** as a destination

### Release date: 23.11.2022

* Extended API. Added multiple endpoints to pull statistics about workflow and task runs

### Release date: 10.11.2022

* Integration with **Salesforce**

### Release date: 01.11.2022

* Cloning of workflows

### Release date: 20.10.2022

* New task "**Filter**"
* A possibility to edit the aggregator's variable name

### Release date: 01.10.2022

* Workflow templates are now visible in the list of workflows and marked with the "template" label

### Release date: 23.09.2022

* Integration with Hubspot Tickets as a destination



