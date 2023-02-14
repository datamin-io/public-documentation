# Using the average value of a metric

One of the most exciting features metrics provide you is the opportunity to compare the current value of the metric with an average value of it within a certain period of time.

Some examples:

<figure><img src="../.gitbook/assets/Screenshot 2023-02-14 at 19.02.45.png" alt=""><figcaption><p>Run a workflow if the current value of the metric is higher than the average one within the last 7 days</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2023-02-14 at 19.04.09.png" alt=""><figcaption><p>Run a workflow if the current value of the metric is higher than the average one within the last 3 months</p></figcaption></figure>

⚠️ The critical thing to keep in mind is that this function only uses the values of this metric from the moment it was created and first run. For example, if you created and scheduled this metric on February 25th and want to calculate an average value, it won't consider the values before that date.

