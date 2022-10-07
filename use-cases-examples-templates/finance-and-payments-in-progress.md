# Finance and payments (in progress)

## Generate commercial reports and send them to BI software or directly to stakeholders

<figure><img src="../.gitbook/assets/Screenshot 2022-10-02 at 00.10.03.png" alt=""><figcaption><p>Possible workflow</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-02 at 00.10.25.png" alt=""><figcaption><p>An SQL example how to retrieve financial data</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-02 at 00.11.07.png" alt=""><figcaption><p>Generated CSV report</p></figcaption></figure>

## Monitoring of failed payments

<figure><img src="../.gitbook/assets/Screenshot 2022-10-06 at 17.35.12.png" alt=""><figcaption><p>Possible workflow</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-06 at 17.35.31.png" alt=""><figcaption><p>Possible data query</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-06 at 17.36.10.png" alt=""><figcaption><p>Slack notifications</p></figcaption></figure>

## Monitor overpaid orders

In case an organization accepts payments from customers with the direct bank transfers, it opens us a potential for mistakes made in the references or amount.

The following workflow can help to control and find overpaid orders or invoices.

<figure><img src="../.gitbook/assets/Screenshot 2022-10-07 at 17.38.00.png" alt=""><figcaption><p>Potential workflow</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-07 at 17.38.18.png" alt=""><figcaption><p>Potential SQL query to retrieve data</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-07 at 17.38.43.png" alt=""><figcaption><p>Potential message to send to stakeholders</p></figcaption></figure>

## Filtering data sets by various values

Filtering data from large data sets is one of the most common and important tasks for payment operations. One of the powerful instruments Datamin offers for that is [Transformer](../workflows-and-actions/tasks-ip/transformers.md#extracting-and-filtering-data-with-gjson) with GJSON query language.

Let's imagine we have the following dataset and we need to filter it in various ways:

```json
[
   {
      "amount":250,
      "created_at":"2022-10-01 16:01:11",
      "currency":"USD",
      "id":1,
      "organization_id":1,
      "status":"dispatched",
      "updated_at":"2022-10-01 16:01:11"
   },
   {
      "amount":250,
      "created_at":"2022-10-01 16:01:11",
      "currency":"USD",
      "id":2,
      "organization_id":1,
      "status":"paid",
      "updated_at":"2022-10-01 16:01:11"
   },
   {
      "amount":3677.2,
      "created_at":"2022-10-01 16:01:11",
      "currency":"USD",
      "id":3,
      "organization_id":2,
      "status":"completed",
      "updated_at":"2022-10-01 16:01:11"
   },
   {
      "amount":21.87,
      "created_at":"2022-10-01 16:01:11",
      "currency":"EUR",
      "id":4,
      "organization_id":1,
      "status":"assembled",
      "updated_at":"2022-10-01 16:01:11"
   },
   {
      "amount":21.87,
      "created_at":"2022-10-01 16:01:11",
      "currency":"EUR",
      "id":5,
      "organization_id":4,
      "status":"assembled",
      "updated_at":"2022-10-01 16:01:11"
   },
   {
      "amount":341.76,
      "created_at":"2022-10-01 16:01:11",
      "currency":"EUR",
      "id":6,
      "organization_id":1,
      "status":"complete",
      "updated_at":"2022-10-01 16:01:11"
   },
   {
      "amount":2110.76,
      "created_at":"2022-10-01 16:01:11",
      "currency":"USD",
      "id":7,
      "organization_id":3,
      "status":"new",
      "updated_at":"2022-10-01 16:01:11"
   },
   {
      "amount":127.89,
      "created_at":"2022-10-01 16:01:11",
      "currency":"USD",
      "id":8,
      "organization_id":3,
      "status":"new",
      "updated_at":"2022-10-01 16:01:11"
   },
   {
      "amount":127.9,
      "created_at":"2022-10-01 16:01:11",
      "currency":"EUR",
      "id":9,
      "organization_id":4,
      "status":"new",
      "updated_at":"2022-10-01 16:01:11"
   },
   {
      "amount":344.44,
      "created_at":"2022-10-01 16:01:11",
      "currency":"USD",
      "id":10,
      "organization_id":5,
      "status":"paid",
      "updated_at":"2022-10-01 16:01:11"
   }
]
```

Let's look at the following 4 examples:

<figure><img src="../.gitbook/assets/Screenshot 2022-10-06 at 14.12.18.png" alt=""><figcaption></figcaption></figure>

```json
Filter: 
#(status == "assembled")#

Result:
[
   {
      "amount":21.87,
      "created_at":"2022-10-01 16:01:11",
      "currency":"EUR",
      "id":4,
      "organization_id":1,
      "status":"assembled",
      "updated_at":"2022-10-01 16:01:11"
   },
   {
      "amount":21.87,
      "created_at":"2022-10-01 16:01:11",
      "currency":"EUR",
      "id":5,
      "organization_id":4,
      "status":"assembled",
      "updated_at":"2022-10-01 16:01:11"
   },
   {
      "amount":67.01,
      "created_at":"2022-10-01 16:01:11",
      "currency":"EUR",
      "id":12,
      "organization_id":2,
      "status":"assembled",
      "updated_at":"2022-10-01 16:01:11"
   }
]

Filter:
#(status == "assembled")#.amount

Result:
[
   21.87,
   21.87,
   67.01
]

Filter:
#(status == "assembled").amount

Result: 21.87

Filter: 
#(amount < 30)#

Result: 
[
   {
      "amount":21.87,
      "created_at":"2022-10-01 16:01:11",
      "currency":"EUR",
      "id":4,
      "organization_id":1,
      "status":"assembled",
      "updated_at":"2022-10-01 16:01:11"
   },
   {
      "amount":21.87,
      "created_at":"2022-10-01 16:01:11",
      "currency":"EUR",
      "id":5,
      "organization_id":4,
      "status":"assembled",
      "updated_at":"2022-10-01 16:01:11"
   }
]
```
