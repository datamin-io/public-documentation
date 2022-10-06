# Customer Success

## Drop in user signups

The following workflow example helps to retrieve all signups from today, compare the number of them with the target and notify the customer success team if it is lower than expected:

<figure><img src="../.gitbook/assets/Screenshot 2022-10-06 at 14.48.30.png" alt=""><figcaption><p>Workflow example</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-06 at 14.49.00.png" alt=""><figcaption><p>Query task</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-06 at 14.49.47.png" alt=""><figcaption><p>Condition task</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-06 at 14.50.04.png" alt=""><figcaption><p>Notification task</p></figcaption></figure>

## Drop in user logins

The same monitoring can be implemented for user logins. Just the query needs to be based on a different field:

<figure><img src="../.gitbook/assets/Screenshot 2022-10-06 at 14.33.10.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-06 at 14.51.21.png" alt=""><figcaption></figcaption></figure>

## Monitor customers stuck in the onboarding

<figure><img src="../.gitbook/assets/Screenshot 2022-10-06 at 14.59.58.png" alt=""><figcaption><p>Example workflow</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-06 at 15.01.26.png" alt=""><figcaption><p>Query task</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-06 at 15.02.06.png" alt=""><figcaption><p>CSV report as a result</p></figcaption></figure>

## Customer engagement summary report

<figure><img src="../.gitbook/assets/Screenshot 2022-10-06 at 15.32.58.png" alt=""><figcaption><p>Workflow example</p></figcaption></figure>

```sql
// Simple SQL to get data
SELECT
  COUNT(*) as cnt,
  status
FROM customer_success.users
GROUP BY status
ORDER by cnt DESC;
```

And the the result can be sent once per a period of time (usually week) to your customer success team.
