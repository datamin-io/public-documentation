# E-mail

{% hint style="info" %}
If you use open-source or on-premise edition of Ylem, see [below](e-mail.md#configuring-e-mail-sending-integration-for-open-source-and-cloud-based-edition) how to configure this integration.
{% endhint %}

**Integration type**:  `Write`

E-mail integration allows you to send files, reports, and data in other formats via Email. To send E-mails to someone's address you need to have access to these e-mails to verify it.&#x20;

**Data for the connection:**

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-23 at 18.59.18.png" alt=""><figcaption></figcaption></figure>

## Configuring E-mail sending integration for open-source and cloud-based edition

If you use open-source of cloud-based edition of Ylem, you need to configure an integration with your E-mail sending provider.

In case you use Amazon SES, what you just need to do, is do add the following parameters to the environment file `./env.common`

```bash
AWS_REGION=
AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
```

If you use an alternative E-mail sending provider, the best way to integrate with it is to use an [API Integration](apis.md).
