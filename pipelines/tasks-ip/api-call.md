# API Call

The "**API Call"** can be used at the beginning of the pipeline to read data from a certain API Endpoint and also at the end to send data to a certain external or internal API. API Endpoints are configured in the [integrations](../../integrations/library-of-integrations/apis.md).

The task supports all the attributes of a normal API Call when it is done from the command line using `curl` or a software like `Postman`, such as body payload, headers, and query strings.

Here is an example of how to use it for sending some input data in the Body of the POST request:

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 21.47.26.png" alt=""><figcaption></figcaption></figure>

You can also attach files, dynamically created from the input dataset to it. For example, if in front of the "**API call**" you place a "[Transformer](transformers.md)" that converts input to CSV, the result can be sent further as a .csv file.

<div align="center">

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 21.50.11.png" alt=""><figcaption></figcaption></figure>

</div>
