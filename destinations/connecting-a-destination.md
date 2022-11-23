# Connecting a destination

**Destinations** are channels where you can send alerts, messages, files, and other outputs of your workflows. It can also be your own APIs you trigger to change data and automate actions or external APIs of the software used in your organization.\
\
At the moment Datamin supports the following 3 main categories of destinations.

### Generic destinations

* **Email.** Typically used for sending CSV and XML reports, data sets, and other kinds of notifications.
* **SMS.** Typically used for sending critical alarms and messages about incidents that must be solved as soon as possible.

{% hint style="info" %}
In the case of **SMS** and **Email**, we will also ask you to verify a phone and an E-mail address in order to make sure that the owner allows messages to be sent.
{% endhint %}

### Custom software

* **Slack**. For sending messages to specific channels
* **Tableau**. For sending data to be used in graphs, diagrams, and reports
* **Atlassian Jira**. For creating support and bug tickets for engineering and product teams.
* ****[**Hubspot**](connecting-a-hubspot.md). For creating tickets for revenue teams.
* **Incident.io**. For creating data incidents to be solved by your team in Slack.
* **Salesforce**. For creating tickets for revenue teams.
* **Google Sheets**. For saving data to Google Sheets

### API Calls

**API Calls** can be used for a wide range of purposes. You can trigger API endpoints of your backend, **API Gateways** in clouds, **CRM** systems such as **Salesforce**, or even deployment systems such as **Jenkins**.

<figure><img src="../.gitbook/assets/Screenshot 2022-09-14 at 22.58.56.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2022-09-14 at 22.58.22.png" alt=""><figcaption></figcaption></figure>
