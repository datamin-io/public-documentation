# E-commerce & Logistics

## Generate commercial report and send it to BI software or directly to stakeholders

<figure><img src="../.gitbook/assets/Screenshot 2022-10-01 at 23.40.47.png" alt=""><figcaption><p>Possible workflow</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-01 at 23.41.05.png" alt=""><figcaption><p>An example how to retrieve data as SQL</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-01 at 23.43.31.png" alt=""><figcaption><p>Generared CSV report</p></figcaption></figure>

## SLA monitoring for order deliveries

With Datamin it is very easy to monitor KPIs but also SLAs for various cases. One of the examples for e-commerce specifically is to detect orders which are not delivered within SLA time.

<figure><img src="../.gitbook/assets/Screenshot 2022-10-07 at 19.13.03.png" alt=""><figcaption><p>Potential SLA monitoring workflow</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-07 at 19.13.37.png" alt=""><figcaption><p>Potential SQL query to retrieve data</p></figcaption></figure>

## Monitor overpaid orders

In case an organization accepts payments from customers with direct bank transfers, it opens a potential for mistakes made in the references or amount.

The following workflow can help to control and find overpaid orders.

<figure><img src="../.gitbook/assets/Screenshot 2022-10-10 at 18.11.52.png" alt=""><figcaption><p>Potential workflow</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-10 at 18.12.02.png" alt=""><figcaption><p>Potential SQL query</p></figcaption></figure>

## Warehouse stock monitoring

With Datamin you can control the size of your stock and send alerts to the operational teams if it is necessary to restock some items:

<figure><img src="../.gitbook/assets/Screenshot 2022-10-10 at 18.19.31.png" alt=""><figcaption><p>Example of the workflow</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-10-10 at 18.28.35.png" alt=""><figcaption><p>Example of the message to the ops team</p></figcaption></figure>

## Filtering data sets by various values

Filtering data from large data sets is one of the most common and important tasks for e-commerce operations. One of the powerful instruments Datamin offers for that is [Transformer](../workflows/tasks-ip/transformers.md#extracting-and-filtering-data-with-gjson) with GJSON query language.

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
