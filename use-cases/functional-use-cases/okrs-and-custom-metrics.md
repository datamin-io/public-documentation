# OKRs and custom metrics

The functionality of [Datamin's metrics](broken-reference) allows you to set up actions based on the values of various data KPIs, OKRs, SLAs, or any other custom metric you use in your organization.

## Objectives and Key Results (OKRs)

OKRs (Objectives and Key Results) is a performance management framework that encourages companies to set, communicate, and monitor broad organizational goals and results. The framework is meant to be transparent and to align the business, team, and individual objectives in a hierarchal, measurable way.

Datamin's framework of metrics and pipelines perfectly fits the task of converting OKRs to practical automated actions.

## HR OKR. Number of monthly hires

Retrieve data from the data source, where you store your HR data. It can be an API of Personio, BambooHR your custom DWH, or any other data storage

<figure><img src="../../.gitbook/assets/Screenshot 2023-01-15 at 20.29.24.png" alt=""><figcaption></figcaption></figure>

And then calculated the number of items with the aggregated function COUNT():

<figure><img src="../../.gitbook/assets/Screenshot 2023-01-15 at 20.29.33.png" alt=""><figcaption></figcaption></figure>

## Customer success OKR. Number of sign-ins per month

First, you need to retrieve data from your data source when sign-ins are in the current month:

<figure><img src="../../.gitbook/assets/Screenshot 2023-01-15 at 20.34.02.png" alt=""><figcaption></figcaption></figure>

And then as same as in the previous example, to calculate a number of it:

<figure><img src="../../.gitbook/assets/Screenshot 2023-01-15 at 20.34.10.png" alt=""><figcaption></figcaption></figure>

## Marketing OKR. The average number of website actions per user

<figure><img src="../../.gitbook/assets/Screenshot 2023-01-15 at 20.36.30.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2023-01-15 at 20.36.37.png" alt=""><figcaption></figcaption></figure>

## Sales or Operations OKR. Monthly shipped amount

<figure><img src="../../.gitbook/assets/Screenshot 2023-01-15 at 20.42.30.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2023-01-15 at 20.42.39.png" alt=""><figcaption></figcaption></figure>
