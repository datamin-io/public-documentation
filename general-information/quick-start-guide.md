# Quick start guide

The shortest path to start streaming data with Datamin is to integrate with the source from where you want to stream, with the destination to where you want to stream and build a streaming pipeline for it.

Let's create two simple pipeline examples.&#x20;

The first pipeline will stream from a database to an API and will be run by a schedule. The second one will stream from Apache Kafka to a database and will be triggered from Kafka when a new message arrives on a topic.

## Example 1. Streaming from a database to an API

Let's imagine, you have a PostgreSQL database and you want to stream new invoices from it to an API of your internal financial software.

Our goal here would be to build a pipeline like this:

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 14.34.19.png" alt=""><figcaption></figcaption></figure>

Before that, let's start with creating a connection to the PostgreSQL and an API Endpoint, you want to stream to.

### Adding PostgreSQL integration:

1. Open the [list of integrations](https://app.datamin.io/integrations)
2. Click on "**Add integration**"
3. Select '**PostgreSQL**"
4. Fill in your connection details to the form as described [here](../integrations/library-of-integrations/postgresql.md)
5. Click on "**Save**"
6. To make sure that the connection works, you can also click on "**Test connection**" and fix the details if you get an error.

### Adding API integration:

Now repeat the same procedure for the API integration.

1. Open the [list of integrations](https://app.datamin.io/integrations)
2. Click on "**Add integration**"
3. Select '**API**"
4. Fill in your connection details to the form as described [here](../integrations/library-of-integrations/apis.md)
5. Click on "**Save**"

### Creating a pipeline

When both integrations are created, you can create the pipeline itself.

1. Go to the [list of pipelines](https://app.datamin.io/pipelines)
2. Click on "**Add pipeline**" -> "**Create blank**"
3. Drag and drop four tasks on the canvas: [Query](../pipelines/tasks-ip/query.md), [Condition](../pipelines/tasks-ip/condition.md), [For\_each](../pipelines/tasks-ip/for-each.md), [API Call](../pipelines/tasks-ip/api-call.md) and connect them as shown in the picture below:

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 14.34.19.png" alt=""><figcaption></figcaption></figure>

4. Configure the "**Query**" task. Select the database integration you created on the first step and configure how you want to retrieve data from it.&#x20;

For this example, we will select all invoices that were created within the last 30 minutes. We use the [UI constructor](../pipelines/tasks-ip/query.md), but you can, of course, use plain SQL as well.

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 14.32.18.png" alt=""><figcaption></figcaption></figure>

5. Configure the "**Condition**" task. Let's make sure that the dataset is not empty before we move it further through the pipeline:

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 14.57.33.png" alt=""><figcaption></figcaption></figure>

6. If the condition is true and the input dataset is not empty, the "**For\_each**" task will split it into separate items and send them to the "**API\_call**" one by one. No additional configuration is needed for this task.
7. Last but not least, let's configure the "**API\_call**" task. Select the API Endpoint, you configured in the second step and describe the JSON, you want to send to it. For example, like this:

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 14.57.49.png" alt=""><figcaption></figcaption></figure>

### Running and testing the pipeline

Now when we are done with creating the pipeline, you can run it manually and test if everything works as expected.&#x20;

Click on "**Run pipeline**" in the top right corner.

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 14.58.09.png" alt=""><figcaption></figcaption></figure>

The pipeline will start running and you will see the status of each task in real-time:

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 15.03.52.png" alt=""><figcaption></figcaption></figure>

You can also click on "**Show output log**" in the same corner:

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 15.04.11.png" alt=""><figcaption></figcaption></figure>

It will display the entire log in plain text format:

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 15.04.20.png" alt=""><figcaption></figcaption></figure>

As you can see, my "**Query**" returns 0 rows and the pipeline doesn't pass through the "**Condition**" task. It can be also seen in the output for each task individually:

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 15.05.16.png" alt=""><figcaption></figcaption></figure>

It means I need to check my "**Query**" or simply go to my database and make sure I have the right data in place. When it is fixed, the "**Query**" task will start showing the correct output:

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 15.13.19.png" alt=""><figcaption></figcaption></figure>

### Scheduling the pipeline

Now, when we make sure that our pipeline works and is tested, we can decide how we want to automate the execution of it.&#x20;

Close the canvas and go to "**Triggers**":

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 15.15.38.png" alt=""><figcaption></figcaption></figure>

Datamin is an agile software and supports multiple ways of triggering the pipeline.

Let's not focus on all of them for the quick start purpose, more information can be found in the [pipeline documentation](../pipelines/running-and-scheduling-workflows.md).

For this particular pipeline, let's say we want to run it twice per hour at 00th and 30th minutes. Click on "**Edit pipeline schedule**", configure this schedule in the form, and click on "**Save**".

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 15.18.22.png" alt=""><figcaption></figcaption></figure>

Now, when the pipeline is scheduled, you can follow its [statistics and execution log](../statistics-and-profiling/statistics-of-runs.md) by clicking on its tabs:

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 15.15.38 (1).png" alt=""><figcaption></figcaption></figure>

## Example 2. Streaming from Apache Kafka to a database

Now that you are familiar with the basic concepts of how to set up data streaming with Datamin, you can learn more about

* [Integrations](broken-reference)
* [Pipelines](broken-reference)
* [Metrics](broken-reference)
* [Use cases](../use-cases/use-cases.-homepage.md)
* [Statistics and profiling](broken-reference)
* [API](broken-reference)

