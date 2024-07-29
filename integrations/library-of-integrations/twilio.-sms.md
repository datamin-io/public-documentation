# Twilio. SMS

**Integration type**:  `Write`

Datamin supports sending critical SMS alerts to the verified phone numbers of members of your organization.

**Data for the connection:**

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-28 at 18.58.30.png" alt=""><figcaption></figcaption></figure>

### On-Premise/Open-Source Configuration

If you use on-premise or open-source editions of Datamin, to be able to use this task, you need to create your own [Twilio](https://www.twilio.com/) account and configure the following parameters:

```bash
YLEM_INTEGRATIONS_TWILIO_ACCOUNT_SID=
YLEM_INTEGRATIONS_TWILIO_AUTH_TOKEN=
YLEM_INTEGRATIONS_TWILIO_NUMBER_FROM=
```

The following variables need to be placed in the root folder file `./.env`.common

Read more about setting up Twilio auth token and account sid [here](https://www.twilio.com/en-us/messaging/programmable-messaging-api).

Accounts and API tokens can be viewed in the Twilio dashboard here: [https://console.twilio.com/us1/account/keys-credentials/api-keys](https://console.twilio.com/us1/account/keys-credentials/api-keys)
