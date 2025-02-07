# Configuring integrations with .env variables

The open-source edition of Ylem enables you to configure some integrations by creating your accounts there first and then using credentials such as tokens, API keys, or secret keys in Ylem's environment variables to make it work.

On this page, we describe all such integrations and the environment variables you need to configure to make them work. However, you can also find necessary information at the global `.env.common` file in the root folder or the `.env` files of every microservice.

## User authentication with Google

If you want to enable user authentication in Ylem's UI through Google, you need to configure the following parameters in the `.env` file (`./backend/users/.env` if you build Ylem from the source):

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

The following two variables need to be placed in the`.env` file ( or `./processor/taskrunner/.env`if you build Ylem from the source). Read more about [API Keys](https://platform.openai.com/api-keys) and [available models](https://platform.openai.com/docs/models) in the official OpenAI reference guide.

## Using Twilio to send SMS from pipelines

If you want to [send an SMS from the pipeline Notification task](../integrations/library-of-integrations/twilio.-sms.md), you need to create your own [Twilio](https://www.twilio.com/) account and configure the following parameters:

```bash
YLEM_INTEGRATIONS_TWILIO_ACCOUNT_SID=
YLEM_INTEGRATIONS_TWILIO_AUTH_TOKEN=
YLEM_INTEGRATIONS_TWILIO_NUMBER_FROM=
```

The following variables need to be placed in the root folder `.env` file (or `./.env.common`if you build Ylem from the source).&#x20;

Read more about setting up Twilio auth token and account side [here](https://www.twilio.com/en-us/messaging/programmable-messaging-api).

Accounts and API tokens can be viewed in the Twilio dashboard here: [https://console.twilio.com/us1/account/keys-credentials/api-keys](https://console.twilio.com/us1/account/keys-credentials/api-keys)

## Using AWS KMS to encrypt/decrypt data

Ylem supports integration with AWS KMS for encrypting/decrypting information about users, organizations, and integration credentials.

The following variables need to be placed in the root folder `.env` file ( or`./.env.common`if you build Ylem from the source).

```bash
AWS_KMS_KEY_ID= 
AWS_REGION= 
AWS_ACCESS_KEY_ID= 
AWS_SECRET_ACCESS_KEY=
```

This integration is optional and if these variables are left empty, the information will be stored unencrypted.

## Sending E-mails with Amazon SES

The same variables in the `.env` file (`./env.common` for building Ylem from the source) can be used to enable E-mail sending with Amazon SES:

```bash
AWS_REGION=
AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
```

More information about it can be found on the [E-mail integration page](../integrations/library-of-integrations/e-mail.md#configuring-e-mail-sending-integration-for-open-source-and-cloud-based-edition).

## OAuth 2.0 Integrations

### Atlassian Jira

The following parameters need to be changed on the `.env` file (or`backend/integrations/.env` for building Ylem from the source):

```bash
INTEGRATIONS_JIRA_OAUTH_CLIENT_ID=%%REPLACE_IT_WITH_THE_CLIENT_ID_OF_YOUR_APP%%
INTEGRATIONS_JIRA_OAUTH_CLIENT_SECRET=%%REPLACE_IT_WITH_THE_CLIENT_SECRET_OF_YOUR_APP%%
INTEGRATIONS_JIRA_AFTER_AUTHORIZATION_REDIRECT_URL=https://%%REPLACE_IT_WITH_THE_DOMAIN_NAME_OF_YOUR_YLEM_INSTANCE%%/jira-authorizations/{uuid}/?justConnected
```

The full information on enabling Atlassian Jira integration for the open-source edition is available on the [integration page](../integrations/library-of-integrations/atlassian-jira.md#configuring-integration-for-open-source-and-on-premise-versions).

### Hubspot

The following parameters need to be changed on the `.env` file (or`backend/integrations/.env`  for building Ylem from the source):

```bash
INTEGRATIONS_HUBSPOT_OAUTH_CLIENT_ID=%%REPLACE_IT_WITH_THE_CLIENT_ID_OF_YOUR_APP%%
INTEGRATIONS_HUBSPOT_OAUTH_CLIENT_SECRET=%%REPLACE_IT_WITH_THE_CLIENT_SECRET_OF_YOUR_APP%%
INTEGRATIONS_HUBSPOT_AFTER_AUTHORIZATION_REDIRECT_URL=https://%%REPLACE_IT_WITH_THE_DOMAIN_NAME_OF_YOUR_YLEM_INSTANCE%%/hubspot-authorizations/{uuid}/?justConnected
```

The full information on enabling Hubspot integration for the open-source edition is available on the [integration page](../integrations/library-of-integrations/hubspot.md#configuring-integration-for-open-source-and-on-premise-versions).

### Salesforce

The following parameters need to be changed on the `.env` file (or`backend/integrations/.env`  for building Ylem from the source):

```bash
INTEGRATIONS_SALESFORCE_OAUTH_CLIENT_ID=%%REPLACE_IT_WITH_THE_CLIENT_ID_OF_YOUR_APP%%
INTEGRATIONS_SALESFORCE_OAUTH_CLIENT_SECRET=%%REPLACE_IT_WITH_THE_CLIENT_SECRET_OF_YOUR_APP%%
INTEGRATIONS_SALESFORCE_AFTER_AUTHORIZATION_REDIRECT_URL=https://%%REPLACE_IT_WITH_THE_DOMAIN_NAME_OF_YOUR_YLEM_INSTANCE%%/salesforce-authorizations/{uuid}/?justConnected
```

The full information on enabling Salesforce integration for the open-source edition is available on the [integration page](../integrations/library-of-integrations/salesforce.md#configuring-integration-for-open-source-and-on-premise-versions-using-oauth-2.0).

### Slack

The following parameters need to be changed on the `.env` file (or`backend/integrations/.env`  for building Ylem from the source):

```bash
INTEGRATIONS_SLACK_OAUTH_CLIENT_ID=%%REPLACE_IT_WITH_THE_CLIENT_ID_OF_YOUR_APP%%
INTEGRATIONS_SLACK_OAUTH_CLIENT_SECRET=%%REPLACE_IT_WITH_THE_CLIENT_SECRET_OF_YOUR_APP%%
INTEGRATIONS_SLACK_AFTER_AUTHORIZATION_REDIRECT_URL=https://%%REPLACE_IT_WITH_THE_DOMAIN_NAME_OF_YOUR_YLEM_INSTANCE%%/salesforce-authorizations/{uuid}/?justConnected
```

The full information on enabling Slack integration for the open-source edition is available on the [integration page](../integrations/library-of-integrations/slack.md#configuring-integration-for-open-source-and-on-premise-versions).
