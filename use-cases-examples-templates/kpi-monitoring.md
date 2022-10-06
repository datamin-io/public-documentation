# KPI monitoring

## General KPI monitoring

Datamin provides an extremely powerful way of calculating various KPIs from commonly known metrics (ARR, MRR, LTV, etc) to custom ones, that you can define on your own.

Metrics can be calculated in the [Query](../workflows-and-actions/tasks-ip/#query) itself or using an [Aggregator](../workflows-and-actions/tasks-ip/#aggregator).

Typically the result is compared with a certain target and sent as a notification to **Slack** or channels afterward.

<figure><img src="../.gitbook/assets/Screenshot 2022-10-01 at 18.23.31.png" alt=""><figcaption><p>Potential workflow</p></figcaption></figure>

## ARR Monitoring

<figure><img src="../.gitbook/assets/Screenshot 2022-10-01 at 18.12.44.png" alt=""><figcaption><p>Potential workflow</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-01 at 18.13.09.png" alt=""><figcaption><p>Potential data extraction</p></figcaption></figure>

## MRR monitoring

<figure><img src="../.gitbook/assets/Screenshot 2022-10-01 at 18.28.29.png" alt=""><figcaption><p>Potential workflow</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-01 at 18.28.48.png" alt=""><figcaption><p>Potential data extraction</p></figcaption></figure>

## Monitor average value per customer

Datamin allows easy monitoring of average values (amounts, orders, bank transfers, contract values) per customer. As an example the following workflow represents the calculation of an average amount per customer and taking actions for different sizes of it:

<figure><img src="../.gitbook/assets/Screenshot 2022-10-06 at 17.21.28.png" alt=""><figcaption><p>Workflow example</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-06 at 17.22.03.png" alt=""><figcaption><p>Possible SQL query</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-06 at 17.22.19.png" alt=""><figcaption><p>Possible filter task</p></figcaption></figure>
