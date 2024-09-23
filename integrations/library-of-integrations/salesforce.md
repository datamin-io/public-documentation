# Salesforce

{% hint style="info" %}
This integration is only available in open-source and on-premise editions. Please contact us, if you want to have Salesforce in the cloud edition for you organization.
{% endhint %}

**Integration type**:  `Write`

With Salesforce integration you can stream data and create Salesforce tickets in real-time.

If you need to stream flexible data directly to Salesforce API, consider using [API integration](apis.md) instead.

## Configuring integration for open-source and on-premise versions using OAuth 2.0

### Step 1. Salesforce Connected App and authorizing Ylem to have access to user's account

You need to create your own Salesforce Connected App first and integrate your Ylem instance with it so that your users will be able to authorize Ylem to access their Salesforce account data.

Here you can read more about how to create a [connected APP](https://help.salesforce.com/s/articleView?id=sf.connected\_app\_create.htm\&type=5) and manage [OAuth 2.0 authentication](https://help.salesforce.com/s/articleView?id=sf.remoteaccess\_authenticate.htm\&type=5) with Salesforce.

{% hint style="info" %}
Please note, that a Salesforce user must be assigned to the system permissions "**API Enabled**", and "**Apex REST Services**"
{% endhint %}

As soon as the application is created, you will get OAuth 2.0 `CLIENT_ID` and `CLIENT_SECRET` that must be placed into the `./backend/integrations/.env` file of Ylem together with the redirect URL to your Ylem instance:

```bash
INTEGRATIONS_SALESFORCE_OAUTH_CLIENT_ID=%%REPLACE_IT_WITH_THE_CLIENT_ID_OF_YOUR_APP%%
INTEGRATIONS_SALESFORCE_OAUTH_CLIENT_SECRET=%%REPLACE_IT_WITH_THE_CLIENT_SECRET_OF_YOUR_APP%%
INTEGRATIONS_SALESFORCE_AFTER_AUTHORIZATION_REDIRECT_URL=https://%%REPLACE_IT_WITH_THE_DOMAIN_NAME_OF_YOUR_YLEM_INSTANCE%%/salesforce-authorizations/{uuid}/?justConnected
```

Now you can open **https://%%YOUR\_YLEM\_DOMAIN\_NAME%%/salesforce-authorizations** and try to authorize Salesforce Integration by clicking on the button "**Add Salesforce authorization**".&#x20;

If configured correctly, after the redirection to Salesforce and giving the permissions, you will get back to the same page with the new authorization appeared in the list:

<figure><img src="../../.gitbook/assets/Screenshot 2024-09-23 at 17.39.19.png" alt=""><figcaption></figcaption></figure>

### Step 2. Creating a new integration with Salesforce

Now the same aithorization can be used for [creating new integrations](https://app.datamin.io/integrations).&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-23 at 19.01.22.png" alt=""><figcaption></figcaption></figure>
