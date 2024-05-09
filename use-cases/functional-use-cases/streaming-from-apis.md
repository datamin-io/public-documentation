# Streaming from APIs

For streaming data from APIs, you need to read data in your pipeline with the "[API call](../../pipelines/tasks-ip/api-call.md)" task:



<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 20.22.56.png" alt=""><figcaption></figcaption></figure>

When the pipeline is triggered, this task will make an API request to the API Endpoint, you have configured in your [API integration](../../integrations/library-of-integrations/apis.md) and use the response data for the entire pipeline.

&#x20;Some examples of the streaming pipelines from the API:

## Streaming from API to a database

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-09 at 20.09.12.png" alt=""><figcaption></figcaption></figure>

## Streaming from API to API

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-09 at 20.10.49.png" alt=""><figcaption></figcaption></figure>

Of course, the pipelines above are just examples and your real pipelines will most probably be more complicated and will contain more transformation and processing of data:

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-09 at 20.16.13.png" alt=""><figcaption></figcaption></figure>

