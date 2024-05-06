# Finance and Payments

The financial industry is an industry where an organization needs to know about any good or positive event related to customers' accounts as fast as possible. Therefore receiving such information is a real-time mode is vital for many departments from BI to risk, operations, or compliance. And that's what Datamin is good at.

## Schedule generation of commercial reports and send them to BI software or directly to stakeholders

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-02 at 00.10.03.png" alt=""><figcaption><p>Possible pipeline</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-02 at 00.10.25.png" alt=""><figcaption><p>An SQL example how to retrieve financial data</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-02 at 00.11.07.png" alt=""><figcaption><p>Generated CSV report</p></figcaption></figure>

## Streaming monitoring information about failed payments

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 17.35.12.png" alt=""><figcaption><p>Possible pipeline</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 17.35.31.png" alt=""><figcaption><p>Possible data query</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 17.36.10.png" alt=""><figcaption><p>Slack notifications</p></figcaption></figure>

## Streaming monitoring information about overpaid orders

In case an organization accepts payments from customers with direct bank transfers, it opens a potential for mistakes made in the references or amount.

The following pipeline can help to control and find overpaid orders or invoices.

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-07 at 17.38.00.png" alt=""><figcaption><p>Potential pipeline</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-07 at 17.38.18.png" alt=""><figcaption><p>Potential SQL query to retrieve data</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-07 at 17.38.43.png" alt=""><figcaption><p>Potential message to send to stakeholders</p></figcaption></figure>

## Streaming monitoring information about unallocated bank transfers

Another popular modification of the previous two pipelines is to monitor unallocated bank transfers. This means bank transfers made by customers that the system was not able to allocate to any order, invoice, or any other purchased item.&#x20;

In this case, it is up to you to decide what to do with this transfer. Either return it, try allocating it manually, or contact the customer and ask about it.&#x20;

That's how the typical pipeline may look like:

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-09 at 23.13.52.png" alt=""><figcaption></figcaption></figure>

## Filtering data sets by various factors on the fly

Filtering data from large data sets is one of the most common and important tasks for payment operations. One of the powerful instruments Datamin offers for that is [Transformer](../../pipelines/tasks-ip/transformers.md) with GJSON query language.

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

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 14.12.18.png" alt=""><figcaption></figcaption></figure>

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
