# Running and scheduling workflows

Datamin’s workflows can be triggered in 3 different ways:

### Manually on-demand

<figure><img src="../.gitbook/assets/Screenshot 2022-09-16 at 18.41.11.png" alt=""><figcaption></figcaption></figure>

Both buttons to schedule or run workflow manually are located in the top right corner of the workflow's canvas.&#x20;

Manual trigger is typical for:

* Test workflows, that are used for debugging or testing data sources or destinations
* Workflows that don't have any periodical schedule, but need to be run sometimes when a user needs it

After clicking on `Run workflow` button a user gets an output that shows the status of every task:

<figure><img src="../.gitbook/assets/Screenshot 2022-09-16 at 18.45.18.png" alt=""><figcaption></figcaption></figure>

### Automatically by a schedule

Scheduling is the most common way of triggering workflows. It can be configured using either a visual interface or if you are familiar with a cronjob format, you can also use this one.

<figure><img src="../.gitbook/assets/Screenshot 2022-09-16 at 18.55.53.png" alt=""><figcaption></figcaption></figure>

### Automatically via API.&#x20;

For example, by Apache Airflow, Jenkins, or any other software that is already used in your company for workflow or pipeline orchestration.

More information about triggering workflows via API can be found in the [OAuth Clients](../datamin-api/oauth-clients.md) and [API Endpoints](../datamin-api/api-endpoints.md).
