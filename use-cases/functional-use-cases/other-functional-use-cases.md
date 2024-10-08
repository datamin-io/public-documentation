# Other functional use cases

## Using API as a data source

Ylem not only easily supports any modern database, data warehouse, or any other kind of data storage as a data source but is also very easy to use any API endpoint that returns JSON data as a data source.&#x20;

To do that just configure an [API integration](../../integrations/library-of-integrations/apis.md) first:

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-09 at 22.52.02.png" alt=""><figcaption><p>API integration example</p></figcaption></figure>

And then use it as a first task in the pipeline. The rest works the same way as with any other SQL-based data source.

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-09 at 22.50.44.png" alt=""><figcaption></figcaption></figure>

## Merge data from several sources

Often you don't have all necessary data stored in one storage but rather in a few ones. For example, the ones you have in your production database that are produced by your applications and the ones stored in your CRM.&#x20;

Therefore before taking any action with data, you need to use [Merge](../../pipelines/tasks-ip/merge.md) task:

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-01 at 19.42.20.png" alt=""><figcaption><p>Potential pipeline</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-01 at 19.42.32.png" alt=""><figcaption><p>How to configure merge task</p></figcaption></figure>

## Merge data from several sources consequently

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-01 at 19.54.43.png" alt=""><figcaption><p>Possible pipeline</p></figcaption></figure>

## Data to CSV report

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-01 at 19.57.01.png" alt=""><figcaption><p>Possible pipeline</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-01 at 19.57.22.png" alt=""><figcaption><p>Transforming data to CSV report</p></figcaption></figure>

## Calling API for each entity in the dataset

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-01 at 19.59.44.png" alt=""><figcaption></figcaption></figure>
