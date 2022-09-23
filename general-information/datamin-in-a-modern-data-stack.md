# Datamin in a modern data stack

If we look at the data market from the perspective of **Red/Blue ocean** concepts, it is definitely in the **Red** one.

The existing, competitive, and the crowded market makes it hard for every new Data SaaS to find its place in the market and even harder to explain to customers and investors.

Therefore, let’s look at several existing examples of data stacks and try to find a position for Datamin there.

## Example #1. Traditional BI-oriented data stack <a href="#4219" id="4219"></a>

As reference #1 let’s use a traditional BI-oriented data stack which looks approximately like this:

<figure><img src="../.gitbook/assets/Screenshot 2022-09-15 at 14.39.08.png" alt=""><figcaption></figcaption></figure>

**Google Big Query** or any other DWH if we take a different organization is in the middle of the stack. There are multiple data sources and ETL or ELT software that collects data from these data sources and puts it into the DWH.&#x20;

Afterward, as soon as data are in the data warehouse, **Looker** is connected to it for business intelligence and since it is a part of **Google Cloud** it integrates perfectly with **Google Big Query**.

**dbt** is most probably used for in-warehouse data transformation and this process is orchestrated by **Apache Airflow**.

So, what can we say about this data stack while looking at it?

* First of all, it is pretty much BI and Data Science oriented. Meaning, most probably, the main consumers of data produced and stored by it are data scientists, business analysts, business developers, or managing directors
* At the same time, we don’t see anything responsible for data quality, such as, for example, **Great Expectations**, **Monte Carlo Data,** or any other similar software. It doesn’t mean the company does not use it, but it is not mentioned in the data stack at least
* And there is also a lot of space for real-time operational analytics. ETL, data transformations, and modeling take time and typically operational departments cannot wait for it. Especially if we talk about payment or risk operations from FinTech.

Therefore, there are a few possible use cases for **Datamin** in this data stack.

## Use case #1. Critical operational analytics <a href="#66de" id="66de"></a>

<figure><img src="../.gitbook/assets/Screenshot 2022-09-15 at 14.55.43.png" alt=""><figcaption></figcaption></figure>

Operational software such as **Datamin** has two major goals:

* Automate manual operational tasks as a reaction to changing data
* Immediately notify stakeholders if data produced by operational processes don’t match expectations

To do it effectively **Datamin** must be placed as close as possible to the place where critical data are created to minimize the time gap between creation and reaction. Therefore we connect it here directly to one of the initial data sources. Probably it is a production database (**MySQL**, **PostgreSQL**, **MariaDB**, etc).

In this scenario Datamin can be used for:

* Monitoring data as a result of critical processes and sending alerts to **Slack**, reports to **Emails**, and automatically creating tickets in **Jira**, **Salesforce**, or **Hubspot**. Failed payments, incorrect invoice amounts, stuck deliveries, lost customers, and incorrect bank transfers are just a few examples of such critical data.
* Triggering various internal or external APIs. In this case, Datamin plays the role of middleware between various services developed or used by an organization.

## Use case #2. On-demand or periodical operational analytics <a href="#59ba" id="59ba"></a>

<figure><img src="../.gitbook/assets/Screenshot 2022-09-15 at 15.09.14.png" alt=""><figcaption></figcaption></figure>

However initial data sources might not contain all the data, that are necessary for effective operational analytics and task automation. Yes, of course, Datamin supports multiple connections to various data sources and data sets can be merged right in our workflows, but it is often more effective to just connect **Datamin** to the **Datawarehouse** itself.

This is also a recommended way for tasks that are not time-critical and can be run on demand or with a certain schedule.

Examples of such tasks:

* Generating daily/weekly/monthly financial reports and sending them to CFO/managing directors/shareholders.
* Generating daily summary reports and sending them to ops or data teams.
* Triggering API Endpoints which are responsible for payment allocation, invoice generations, data clean-ups, garbage collection, or any other regular tasks done by an external trigger with certain input data, which is impossible to organize with simple cronjobs.

## Example #2. Poor data stack. <a href="#152e" id="152e"></a>

<figure><img src="../.gitbook/assets/Screenshot 2022-09-15 at 17.03.06.png" alt=""><figcaption></figcaption></figure>

The next example is a poor data stack that is typical for start-ups in the early phase. In this phase start-ups generate a lot of valuable data, but either don’t have the resources to build a proper data stack or simply grow faster than hire data and software engineers.

In such start-ups, a lot of work is done by stakeholders manually. What we hear quite often from such organizations is that their analysts, ops, sales, customer success, or product teams gather data from various sources (production database, CRM, analytics, and tracking software), merge it in **Excel** or **Google Spreadsheets**, and manually upload in **Tableau** or **Looker** for building graphs and diagrams.

And Datamin is here to replace this manual work.

<figure><img src="../.gitbook/assets/Screenshot 2022-09-15 at 17.07.51.png" alt=""><figcaption></figcaption></figure>

Datamin can be connected to SQL-based or API-based data sources, pull data, merge it and send it to Tableau. And this process can be scheduled to run periodically or when certain conditions match. In this case, the role of the operator will be to work with the output generated by Tableau directly.

## Example #3. Advanced data stack, deeply integrated with the organization’s processes and culture. <a href="#b9fc" id="b9fc"></a>

<figure><img src="../.gitbook/assets/Screenshot 2022-09-15 at 17.40.44.png" alt=""><figcaption></figcaption></figure>

Here we can see **Snowflake** as a DWH, **Fivetran** as an ETL software and **Hightouch** as a reverse ETL, **Tableau** for BI, **dbt** for data modeling, and **HEX** for collaborative analysis. We can also add **Apache Airflow** from example #1 as an orchestration software and **Monte Carlo** for data observability.

Such data stacks usually show that the organization invests a lot in data analysis and benefits from it via integrating it into the corporate **decision-making process** which moves the entire data stack to a completely different level of the **corporate culture**. And **Datamin** perfectly fits this mindset.

<figure><img src="../.gitbook/assets/Screenshot 2022-09-15 at 17.53.45.png" alt=""><figcaption></figcaption></figure>

Datamin can be connected to one or many data sources from DWH, and production databases to API-based software such as CRM or backend API. And as soon as it is done, it can be used by data analysis, ops, or data engineers to automate any type of task they have.

Datamin’s workflows can be triggered in 3 different ways:

* Manually on-demand
* Automatically by a schedule
* Automatically via API. For example, by Apache Airflow that is a part of the data stack already.

## Conclusion <a href="#a210" id="a210"></a>

We looked at three examples of modern data stacks. One is more traditional and business intelligence oriented. Another one is poor and typical for start-ups at the beginning of their lifecycle. And the third one is more advanced and is deeply integrated with organizational processes and decision makings.

After looking at it, we found four use cases for how to integrate Datamin into such data stacks and make an effective element of the decision-making data-driven culture in the organization.
