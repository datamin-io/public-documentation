# Pull-Push

A **Pull-Push** pattern represents a situation when a pipeline needs to retrieve (pull) data from one integration, do some processing, and forward (push) it to another destination.

This situation is typical for pipelines that are [run by a schedule](../../pipelines/running-and-scheduling-workflows.md#automatically-by-a-schedule) and proactively pull data from [databases](../../pipelines/tasks-ip/query.md) or [API Endpoints](../../pipelines/tasks-ip/api-call.md) instead of being triggered from outside.

In this example, the pipeline pulls data from a database, checks that the dataset is not empty, does some processing for each of the items, and pushes them to another database one by one.

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-03 at 22.00.01.png" alt=""><figcaption></figcaption></figure>
