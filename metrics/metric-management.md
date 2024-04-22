# Metric management

The functionality of metrics allows you to quickly create OKRs, KPIs, SLAs, and other custom metrics, schedule them, monitor their value, and execute various pipelines based on them.

[Management of metrics](https://app.datamin.io/metrics) consists 5 simple steps:

## Give metric a name

<figure><img src="../.gitbook/assets/Screenshot 2023-01-15 at 22.12.49.png" alt=""><figcaption></figcaption></figure>

## Define how to retrieve data for your metric

As same as in the case of the pipeline task "Query" you can choose between using a visual UI or an SQL interface:

<figure><img src="../.gitbook/assets/Screenshot 2023-01-15 at 22.13.02.png" alt=""><figcaption></figcaption></figure>

## Define how to calculate your metric

[Mathematical functions](../pipelines/mathematical-functions.md) are supported here:

<figure><img src="../.gitbook/assets/Screenshot 2023-01-15 at 22.13.19.png" alt=""><figcaption></figcaption></figure>

## Define how often or when to calculate your metric

<figure><img src="../.gitbook/assets/Screenshot 2023-01-15 at 22.13.38.png" alt=""><figcaption></figcaption></figure>

More scheduling information can be found [here](../pipelines/running-and-scheduling-workflows.md#automatically-by-a-schedule).

## Define thresholds and pipelines to run

And now as the final and most important step, you can define which pipeline to execute depending on the value of your metric:

<figure><img src="../.gitbook/assets/Screenshot 2024-04-17 at 13.56.04.png" alt=""><figcaption></figcaption></figure>



<figure><img src="../.gitbook/assets/Screenshot 2024-04-17 at 13.55.55.png" alt=""><figcaption></figcaption></figure>

Some of the more detailed examples of metrics can be found here in the list of our use cases. Our [library of templates](../pipelines/library-of-templates.md) also contains multiple ones, which you can use for configuring your metrics.
