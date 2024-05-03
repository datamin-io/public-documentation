# Anti-Money Laundering (AML)

Anti-Money Laundering (AML) regulations require businesses to monitor transactions and report suspicious ones to authorities.

Datamin can help you with automating the following critical processes of it:

* Unusual transaction amounts;
* Unusual series of transactions (e.g., a number of cash credits);
* Unusual geographic destination or origin of a payment;&#x20;
* Known threats or typologies.

## Large transaction amounts

Here is an example of the workflow to monitor large transaction amounts

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-10 at 15.40.05.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-10 at 15.39.41.png" alt=""><figcaption><p>Query example to detect large transactions</p></figcaption></figure>

## A high volume of transactions within a short period of time

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-14 at 18.35.30.png" alt=""><figcaption><p>Possible workflow</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-14 at 18.35.46.png" alt=""><figcaption><p>SQL query example to retrieve the number of transactions today grouped by bank account</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-14 at 18.36.18.png" alt=""><figcaption><p>Message to the responsible team</p></figcaption></figure>

## Too many transactions between the same accounts in X days

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-14 at 19.18.30.png" alt=""><figcaption><p>Possible workflow</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-14 at 19.18.39.png" alt=""><figcaption><p>SQL query to retrieve number of transactions between two accounts</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-14 at 19.18.53.png" alt=""><figcaption><p>Message to the responsible team</p></figcaption></figure>

## Other AML use cases

The idea is clear. Using the following examples and templates from our library you can set up your own AML monitoring workflows with SQL queries of any complexity.

Some other examples of what you can monitor with Datamin:

* Users with a high volume of transactions every day
* Transactions from or to suspicious or dangerous locations, which you can define on your own
* Suspicious reference data
* Suspicious bank account owners
* Suspicious and inconsistent activities. For example, a high volume of transactions but following the long breaks
* Unusual amounts per user
* Etc.
