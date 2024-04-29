# Data Issues & Incidents

## Monitoring of missing data

One of the common use cases to monitor with Datamin is missing data in data sets.

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-02 at 00.14.26.png" alt=""><figcaption></figcaption></figure>

The potential workflow is pretty straightforward: get expected data, check if the condition is true or false, and take action. In this particular example, the Condition block checks if the data set is empty or not.

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-02 at 00.14.52.png" alt=""><figcaption></figcaption></figure>

## Monitoring of data consistency

We all know that if an application has a multistep user onboarding process, some of the steps might be skipped or shortcut manually by supporting sales teams.&#x20;

However, it is important to keep all data consistent in order to avoid some of it being missed in the future.

As an example, the following workflow represents monitoring that for all users in the state "complete", questionnaires are in the state "filled".

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-07 at 17.26.42.png" alt=""><figcaption><p>Possible workflow</p></figcaption></figure>

&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-07 at 17.27.04.png" alt=""><figcaption><p>Possible SQL query</p></figcaption></figure>

## Detecting NULLs instead of data

Yes, indeed while creating a table, you can specify that it should not contain NULLs. But it is quite often necessary to lower such strict requirements, for example, when until a certain moment data in a column can be NULL, but should not be NULL after a certain action.

For example, let's take a look at user onboarding in a classical FinTech company. When a user is created in the database, fields like scoring or risk class can be NULL, but after some time when a scoring report is pulled from the 3rd-party scoring provider, these data should be filled. Unless the scoring provider doesn't provide it. And such situations can be monitored with Datamin.

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-10 at 14.46.40.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-10 at 14.45.21.png" alt=""><figcaption><p>Query example</p></figcaption></figure>

## Detecting bugs in code with monitoring of missing data

Missing or broken data can be caused by various reasons:

* Broken data pipelines
* Broken 3rd-party or internal APIs
* Bugs in the code that produces such data

With Datamin it is easily possible to detect all three root causes. To do that, run the following simple workflow, for example, once per minute:

* Retrieve expected data
* Compare it with what you expect to get. For example, the number of items is higher than 0
* If it doesn't match, send a notification alert or take any other necessary action

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-07 at 19.16.23.png" alt=""><figcaption></figcaption></figure>

## Detection of broken data pipelines

In multiple cases, the root cause of missing data is not bugs in the code but broken data pipelines. To control it you can write expectations of how much time can pass between the creation of items in a certain table of your data storage. And if this threshold is passed Datamin will notify your data engineers.

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-09 at 22.36.40.png" alt=""><figcaption><p>Example of a workflow</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-09 at 22.36.51.png" alt=""><figcaption><p>SQL query to calculate difference between the last item's creation and now in seconds</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-09 at 22.37.11.png" alt=""><figcaption><p>An expression to check if that value if higher than 24 hours</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-09 at 22.37.32.png" alt=""><figcaption><p>Notification message for data engineers</p></figcaption></figure>
