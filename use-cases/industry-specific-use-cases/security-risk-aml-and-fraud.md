# Security, Risk, and Anti-Fraud

## Monitoring of organizations with a high-risk score and streaming them to CRM

Customers who use their own scoring algorithms or rely on 3rd-party scoring providers can use the following pipeline or a modification of it to automate the monitoring of organizations with high-risk scores and call CRM API or send it as a report to the responsible departments.

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 18.04.22.png" alt=""><figcaption><p>Possible pipeline</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 18.04.41.png" alt=""><figcaption><p>Possible data retrieval query</p></figcaption></figure>

## Streaming failed KYC reporting

With this one, you can help your responsible department to automatically detect and take action for customers who failed the KYC procedure.

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 18.18.08.png" alt=""><figcaption><p>Potential pipeline</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-06 at 18.18.33.png" alt=""><figcaption></figcaption></figure>

## Observing and streaming how many users created from the same IP

Potential fraud.

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-07 at 17.34.09.png" alt=""><figcaption><p>Potential pipeline</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-07 at 17.34.24.png" alt=""><figcaption><p>Potential SQL query to retrieve data</p></figcaption></figure>

## Technical real-time detection of XSS attempts

Cross-site scripting (XSS) is a vulnerability that your application should prevent and be secured from. However, automatic XSS attempts can be monitored with Ylem by detecting the word "script" in the database items.&#x20;

In case of detecting your data engineering teams need to block the attack and further improve the application and security to avoid such situations in the future.

Here is an example of a pipeline that will allow you to detect it:

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-10 at 13.51.36.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-10 at 13.51.48.png" alt=""><figcaption><p>SQL query example</p></figcaption></figure>

## Anti-Money Laundering (AML) transaction streaming

Anti-Money Laundering (AML) regulations require businesses to monitor transactions and report suspicious ones to authorities.

Ylem can help you with automating the following critical processes:

* Unusual transaction amounts;
* Unusual series of transactions (e.g., several cash credits);
* Unusual geographic destination or origin of a payment;&#x20;
* Known threats or typologies.

Here is an example of the pipeline to monitor large transaction amounts

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-10 at 15.40.05.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-10 at 15.39.41.png" alt=""><figcaption><p>Query example to detect large transactions</p></figcaption></figure>

More examples of AML use cases are described on a [separate page](anti-money-laundering-aml.md).
