# Atlassian Jira

{% hint style="info" %}
Open-source and On-premise editions of Ylem require separate specific configurations for this integration. See [below](atlassian-jira.md#configuring-integration-for-open-source-and-on-premise-versions)
{% endhint %}

**Integration type**:  `Write`

Integration with Atlassian Jira allows you to create tickets there in real time based on the streaming events you define in Ylem pipelines.

**Data for the connection:**

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-23 at 19.18.19.png" alt=""><figcaption></figcaption></figure>

## Configuring integration for open-source and on-premise versions

If you don't use the cloud version of Ylem but have it installed on your infrastructure under your domain name, you can choose one of the following two ways how to make this integration work.

### Using Atlassian Application and OAuth 2.0

It is the same way how it works in our cloud version. You need to create your own Atlassian Application and integrate your Ylem instance with it so that your users will be able to authorize Ylem to access their Atlassian accounts.

#### Step 1. Create Atlassian Application

As the first step, you need to go to the [Developer Console](https://developer.atlassian.com/console/myapps/) of Atlassian and create your own "OAuth 2.0" application.

<figure><img src="../../.gitbook/assets/Screenshot 2024-09-12 at 21.57.17.png" alt=""><figcaption></figcaption></figure>

These are the data and the scopes required for this application to work with Ylem:



<div>

<figure><img src="../../.gitbook/assets/Screenshot 2024-09-12 at 22.01.55.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Screenshot 2024-09-12 at 22.03.49.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Screenshot 2024-09-12 at 22.03.25.png" alt=""><figcaption></figcaption></figure>

</div>

As soon as the application is ready, you can open its "Settings" and copy your CLIENT\_ID and CLIENT\_SECRET. These two values you will need to add to your Ylem configuration now.

#### Step 2. Configure Ylem .env parameters

The following parameters need to be changed on the `backend/integrations/.env` file:

```bash
INTEGRATIONS_JIRA_OAUTH_CLIENT_ID=%%REPLACE_IT_WITH_THE_CLIENT_ID_OF_YOUR_APP%%
INTEGRATIONS_JIRA_OAUTH_CLIENT_SECRET=%%REPLACE_IT_WITH_THE_CLIENT_SECRET_OF_YOUR_APP%%
INTEGRATIONS_JIRA_AFTER_AUTHORIZATION_REDIRECT_URL=https://%%REPLACE_IT_WITH_THE_DOMAIN_NAME_OF_YOUR_YLEM_INSTANCE%%/jira-authorizations/{uuid}/?justConnected
```

Now you can open **https://%%YOUR\_YLEM\_DOMAIN\_NAME%%/jira-authorizations** and try to authorize Jira Integration by clicking on the button "**Add Jira authorization**".

### Using API integration, Atlassian API, and PAT

Another way of creating an integration with Atlassian Jira to be able to create issues directly from Ylem is using its REST API with Personal Access Tokens (PAT).

#### Step 1. Create Personal Access Token (PAT)

Personal Access Token (PAT) is a safe alternative to using username and password for authentication with various 3rd-party services like Ylem.

This page contains a detailed explanation of how it can be created:

{% embed url="https://confluence.atlassian.com/enterprise/using-personal-access-tokens-1026032365.html" %}

#### Step 2. Creating API Integration and sending requests to it from Ylem pipelines

As soon as you have your PAT configured, you can use it as an Access Token for POST/GET requests to Atlassian API.

Check [Atlassian REST API reference](https://developer.atlassian.com/server/jira/platform/rest/v10000/api-group-issue/#api-api-2-issue-post) and create a Ylem [API Integration](apis.md) with it:

<figure><img src="../../.gitbook/assets/Screenshot 2024-09-12 at 22.15.22.png" alt=""><figcaption></figcaption></figure>

Now you can call it directly from the Ylem pipelines with the necessary query parameters and headers using the [API\_Call](../../pipelines/tasks-ip/api-call.md) task.

<figure><img src="../../.gitbook/assets/Screenshot 2024-09-12 at 22.15.57.png" alt=""><figcaption></figcaption></figure>

