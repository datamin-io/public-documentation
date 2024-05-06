# KPI Monitoring

## General KPI monitoring

Datamin provides an extremely powerful way of calculating various KPIs from commonly known metrics (ARR, MRR, LTV, etc) to custom ones, that you can define on your own.

Metrics can be calculated in the [Query](../../pipelines/tasks-ip/query.md) itself or using an [Aggregator](../../pipelines/tasks-ip/aggregator.md).

Typically the result is compared with a certain target and sent as a notification to **Slack** or channels afterward.

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-01 at 18.23.31.png" alt=""><figcaption><p>Potential pipeline</p></figcaption></figure>

## AVG, SUM, MIN, MAX, and other aggregated monitoring

The pipeline above can be used for monitoring different KPIs represented by mathematical functions such as average values, number of items, minimal and maximal values, etc.&#x20;

More information about using them in [Condition](../../pipelines/tasks-ip/condition.md) and [Aggregator](../../pipelines/tasks-ip/aggregator.md) tasks can be found on a [special separate page](../../pipelines/mathematical-functions.md).



## ARR Monitoring

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-01 at 18.12.44.png" alt=""><figcaption><p>Potential pipeline</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-01 at 18.13.09.png" alt=""><figcaption><p>Potential data extraction</p></figcaption></figure>

## MRR monitoring

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-01 at 18.28.29.png" alt=""><figcaption><p>Potential pipeline</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-01 at 18.28.48.png" alt=""><figcaption><p>Potential data extraction</p></figcaption></figure>

## Stream sales or other revenue KPIs

Sales or other Revenue teams are the most KPI-driven in an organization. Datamin allows easy monitoring of their KPIs, comparing with a target, and taking different actions depending on whether it is already achieved or not yet:

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-07 at 19.24.59.png" alt=""><figcaption><p>Pipeline example for Sales KPIs</p></figcaption></figure>

## Monitor average value per customer

Datamin allows easy monitoring of average values (amounts, orders, bank transfers, contract values) per customer. As an example the following pipeline represents the calculation of an average amount per customer and taking actions for different sizes of it:

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 17.21.28.png" alt=""><figcaption><p>Pipeline example</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 17.22.03.png" alt=""><figcaption><p>Possible SQL query</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 17.22.19.png" alt=""><figcaption><p>Possible filter task</p></figcaption></figure>
