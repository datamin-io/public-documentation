# Data issue monitoring (in progress)

## Monitoring of missing data

One of the common use cases to monitor with Datamin is missing data in data sets.

<figure><img src="../.gitbook/assets/Screenshot 2022-10-02 at 00.14.26.png" alt=""><figcaption></figcaption></figure>

The potential workflow is pretty straightforward: get expected data, check if the condition is true or false, and take action. In this particular example, the Condition block checks if the data set is empty or not.

<figure><img src="../.gitbook/assets/Screenshot 2022-10-02 at 00.14.52.png" alt=""><figcaption></figcaption></figure>

## Monitoring of data consistency

We all know that if an application has a multistep user onboarding process, some of the steps might be skipped or short cut manually by supporting or sales teams.&#x20;

However, it is important to keep all data consistent in order to avoid some of it being missed in the future.

As an example, the following workflow represents monitoring that for all users in the state "complete", questionnaires are in state "filled".

<figure><img src="../.gitbook/assets/Screenshot 2022-10-07 at 17.26.42.png" alt=""><figcaption><p>Possible workflow</p></figcaption></figure>

&#x20;

<figure><img src="../.gitbook/assets/Screenshot 2022-10-07 at 17.27.04.png" alt=""><figcaption><p>Possible SQL query</p></figcaption></figure>

