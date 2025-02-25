# WhatsApp (through Twilio)

**Integration type**: `Write`

Ylem supports sending WhatsApp messages, notifications, and alerts to the phone numbers of members of your organization. You need to create your own Twilio account first.

**Data for the connection:**



<figure><img src="../../.gitbook/assets/Screenshot 2025-02-25 at 11.42.21.png" alt=""><figcaption></figcaption></figure>

### On-Premise/Open-Source Configuration

If you use on-premise or open-source editions of Ylem, to be able to use this task, you need to create your own [Twilio](https://www.twilio.com/) account and configure the following parameters:

```bash
YLEM_INTEGRATIONS_TWILIO_ACCOUNT_SID=
YLEM_INTEGRATIONS_TWILIO_AUTH_TOKEN=
YLEM_INTEGRATIONS_TWILIO_NUMBER_FROM=
```

The following variables need to be placed in the root folder file `./.env`.common

Read more about setting up Twilio auth token and account sid [here](https://www.twilio.com/en-us/messaging/programmable-messaging-api).

Accounts and API tokens can be viewed in the Twilio dashboard here: [https://console.twilio.com/us1/account/keys-credentials/api-keys](https://console.twilio.com/us1/account/keys-credentials/api-keys)
