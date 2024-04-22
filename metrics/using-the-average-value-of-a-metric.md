# Using previous values of a metric

One of the most exciting features metrics provide you is the opportunity to compare the current value of the metric with some values of it within a certain period:

* Metric average
* Metric quantile
* Metric median

Examples:

<figure><img src="../.gitbook/assets/Screenshot 2024-04-17 at 14.01.56.png" alt=""><figcaption><p>Metric average value</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2024-04-17 at 14.02.12.png" alt=""><figcaption><p>Metric quantile</p></figcaption></figure>

More information about these functions can be found on the page of [Mathematical functions](../pipelines/mathematical-functions.md).

⚠️ The critical thing to keep in mind is that this function only uses the values of this metric from the moment it was created and first run. For example, if you created and scheduled this metric on February 25th and want to calculate an average value, it won't consider the values before that date.

