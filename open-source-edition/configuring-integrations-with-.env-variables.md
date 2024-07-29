# Configuring integrations with .env variables

The open-source edition of Datamin enables you to configure some integrations by creating your accounts there first and then using credentials such as tokens, API keys, or secret keys in Datamin's environment variables to make it work.

Here on this page, we describe all of such integrations and the environment variables you need to configure to make it work. However, you can also find necessary information at the global `.env.common` file in the root folder or the `.env` files of every microservice.

## User authentication with Google

If you want to enable user authentication in Datamin's UI through Google, you need to configure the following parameters in the `./backend/users/.env` file:

```sh
USERS_GOOGLE_CLIENT_ID=
USERS_GOOGLE_CLIENT_SECRET=
USERS_GOOGLE_CALLBACK_URL=http://%%YOUR_DOMAIN_NAME_IS_HERE%%/auth/google/callback
```

Read the [following guide](https://developers.google.com/identity/gsi/web/guides/get-google-api-clientid) from Google to configure user authentication and obtain client ID and secret first.

## OpenAI ChatGPT in pipelines

To be able to use [GPT](../pipelines/tasks-ip/gpt.md) task, you need to configure your API Secret Key and choose a model you want to use:

```bash
TASK_RUNNER_OPENAI_GPT_KEY=%%YOUR_KEY_IS_HERE%%
TASK_RUNNER_OPENAI_MODEL=gpt-4o-mini
```

The following two variables need to be placed in the file `./processor/taskrunner/.env`.

Read more about [API Keys](https://platform.openai.com/api-keys) and [available models](https://platform.openai.com/docs/models) in the official OpenAI reference guide.

## Using Twilio to send SMS from pipelines

If you want to [send SMS from the pipeline Notification task](../integrations/library-of-integrations/twilio.-sms.md), you need to create your own [Twilio](https://www.twilio.com/) account and configure the following parameters:

```bash
YLEM_INTEGRATIONS_TWILIO_ACCOUNT_SID=
YLEM_INTEGRATIONS_TWILIO_AUTH_TOKEN=
YLEM_INTEGRATIONS_TWILIO_NUMBER_FROM=
```

The following variables need to be placed in the root folder file `./.env.common`

Read more about setting up Twilio auth token and account side [here](https://www.twilio.com/en-us/messaging/programmable-messaging-api).

Accounts and API tokens can be viewed in the Twilio dashboard here: [https://console.twilio.com/us1/account/keys-credentials/api-keys](https://console.twilio.com/us1/account/keys-credentials/api-keys)
