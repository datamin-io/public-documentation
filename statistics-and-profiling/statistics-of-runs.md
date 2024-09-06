# Statistics of runs

Ylem is a full-cycle data streaming software, therefore not only does it help manage and execute pipelines but also collects detailed statistics of runs for each pipeline and task.

What information is collected:

* Starting time
* Ending time
* Duration in milliseconds
* Task ID and type
* Task output
* Success or failure



<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 13.42.29.png" alt=""><figcaption></figcaption></figure>

Having this information for each of the pipelines Ylem provides users with multiple different ways of working with the statistics:

* A main[ dashboard](https://app.datamin.io/dashboard) that contains accumulated statistics about all pipelines and metrics
* Log of runs for every pipeline and tasks
* Aggregated statistics for every pipeline and task within the selected date range
* Powerful [API to pull statistics](../api/api-endpoints.md) in different forms that can be integrated with your BI software if you want to use these historical data for your reports and dashboards
* [Slow task profiler](slow-tasks.md) that allows you to have constant control over your bottlenecks

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 13.42.39.png" alt=""><figcaption><p>Task output example in the list of logs</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2024-04-30 at 13.43.15.png" alt=""><figcaption><p>Dashboard graph representing the number of new pipelines per month</p></figcaption></figure>
