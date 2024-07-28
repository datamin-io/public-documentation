# GPT

{% hint style="info" %}
:warning: This task is currently only available in the on-premise and open-source editions but not in the cloud version
{% endhint %}

"GPT" is a task that allows you to enrich or transform your data with AI using OpenAI's [chat completion](https://platform.openai.com/docs/guides/chat-completions) models.

### Usage

For example, you have such a pipeline consisting of two tasks:

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-26 at 00.14.42.png" alt=""><figcaption></figcaption></figure>

The first task returns a JSON with the list of items, containing an item ID and amount:

```json
[
    {
        "id": 1,
        "amount": 33
    },
    {
        "id": 2,
        "amount": 150
    },
    {
        "id": 3,
        "amount": 4000
    }
]
```

Now you can ask chat GPT to transform this data. For example, multiply all amounts by 3:

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-26 at 00.13.21.png" alt=""><figcaption></figcaption></figure>

And this is what the task returns:

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-26 at 00.12.56.png" alt=""><figcaption></figcaption></figure>

Of course, such a simple multiplication can be done by other tasks without the use of AI, but that's just an example and you can use ChatGPT for much more. Some other ideas:

* Generate missing postal codes for the list of addresses
* Clean up organization names in the list
* Convert amounts from one currency to another
* Rewrite texts on the fly
* And so on and so on

For example, if you have a list of addresses missing postal codes like this:

```json
[
  {
    "country": "United States",
    "state": "Michigan",
    "city": "Detroit",
    "address": "2645 Woodward Ave"
  },
  {
    "country": "Canada",
    "province": "Alberta",
    "city": "Edmonton",
    "address": "104 Ave NW"
  },
  {
    "country": "United States",
    "state": "Florida",
    "city": "Sunrise",
    "address": "1 Panther Pkwy"
  }
]
```

With the workflow as above and that message to chat GPT:

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-26 at 00.47.48.png" alt=""><figcaption></figcaption></figure>

You will get the perfect result;

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-26 at 00.47.25.png" alt=""><figcaption></figcaption></figure>

### Configuration

To be able to use this task, you need to configure your API Secret Key and choose a model you want to use:

```
TASK_RUNNER_OPENAI_GPT_KEY=%%YOUR_KEY_IS_HERE%%
TASK_RUNNER_OPENAI_MODEL=gpt-4o-mini
```

The following two variables need to be placed in the file `./processor/taskrunner/.env`.

Read more about [API Keys](https://platform.openai.com/api-keys) and [available models](https://platform.openai.com/docs/models) in the official OpenAI reference guide.
