# Customer Success

Customer Success is typically the first department that receives calls from customers. It is your first line of defense that will take the hit when something goes wrong.&#x20;

Therefore notifying them and streaming all the necessary customer information before customer calls to their communication channels and software APIs is important.

## Drop in user signups

The following pipeline example helps to retrieve all signups from today, compare the number of them with the target, and notify the customer success team if it is lower than expected:

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 14.48.30 (1).png" alt=""><figcaption><p>Pipeline example</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 14.49.00.png" alt=""><figcaption><p>Query task</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 14.49.47.png" alt=""><figcaption><p>Condition task</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 14.50.04.png" alt=""><figcaption><p>Notification task</p></figcaption></figure>

## Drop in user logins

The same monitoring can be implemented for user logins. Just the query needs to be based on a different field:

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 14.33.10.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 14.51.21.png" alt=""><figcaption></figcaption></figure>

## Monitor customers stuck in the onboarding

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 14.59.58.png" alt=""><figcaption><p>Example pipeline</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 15.01.26.png" alt=""><figcaption><p>Query task</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 15.02.06 (1).png" alt=""><figcaption><p>CSV report as a result</p></figcaption></figure>

## Customers stuck in the KYC process for too long

One special modification of the previous example is the monitoring of customers who got stuck in the KYC process for too long.&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 18.20.51.png" alt=""><figcaption></figcaption></figure>

If your data source supports such differentiation, you can even automatically detect if the root cause is on your side, your customers' side, or if the problem is related to your KYC provider.

## Customer engagement summary report

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 15.32.58.png" alt=""><figcaption><p>Pipeline example</p></figcaption></figure>

```sql
// Simple SQL to get data
SELECT
  COUNT(*) as cnt,
  status
FROM customer_success.users
GROUP BY status
ORDER by cnt DESC;
```

The result can be sent once per time (usually per week) to your customer success team.
