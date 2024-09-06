# API Reference

As soon as you create your first [OAuth client](oauth-clients.md) and save its client secret you can start integrating Ylem with your application via API.

Currently, the following API endpoints are available:

## Generate OAuth2 token

**Endpoint**

{% code overflow="wrap" %}
```bash
[GET/POST] https://api.datamin.io/v1/oauth/token?client_id=%%CLIENT_ID%%&client_secret=%%CLIENT_SECRET%%&grant_type=client_credentials
```
{% endcode %}

**Request body**\
empty\
\
**Response example**

```json
{
  "access_token": "ZJG5NZFLOWUTYJYWYY0ZOGU3LWI5NZMTYMJLZTJHZJAYNWNJ",
  "expires_in": 86400,
  "refresh_token": "ODQZYTQ2ZMUTOWNHZC01NDG2LWI1ZDMTNZM5YJY1ZWJJZTCW",
  "scope": "workflows:run",
  "token_type": "Bearer"
}
```

## Run pipeline

Pipeline UUID can be found either in the list of pipelines or on the detailed page of the pipeline:

<figure><img src="../.gitbook/assets/Screenshot 2024-04-17 at 13.22.34.png" alt=""><figcaption></figcaption></figure>

**Endpoint**

{% code overflow="wrap" %}
```
POST https://api.datamin.io/v1/pipelines/%%PIPELINE_UUID%%/runs/
```
{% endcode %}

**Request body**\
empty\
\
**Authorization**\
Bearer: %%ACCESS\_TOKEN%%\
\
**Response example**

```json
[
  {
    "id": 40,
    "state": "pending",
    "task_uuid": "449c3c47-427e-465e-b1d2-0bf257b714e4",
    "task_run_uuid": "ec430b94-4e22-4448-94f9-944ec650ba25",
    "workflow_run_uuid": "95295cbc-cee7-49cc-a11a-2f1788423934",
    "is_successful": false,
    "output": null,
    "errors": null,
    "created_at": "",
    "updated_at": "",
  }
]
```

## Get a log of runs for a pipeline

**Endpoint**&#x20;

{% code overflow="wrap" %}
```
GET https://api.datamin.io/v1/stats/pipelines/%%UUID%%/logs/%%DATE_TIME_FROM%%/%%DATE_TIME_TO%%
```
{% endcode %}

**Formatting notice**\
DATE\_TIME\_FROM and DATE\_TIME\_TO must be in the format "Y-m-d H:i:s". For example, "2024-01-01 14:23:01"

**Request body**\
empty\
\
**Authorization**\
Bearer: %%ACCESS\_TOKEN%%\
\
**Response example**

```
[
    {
        "workflow_run_uuid": "f05eeffa-1683-4dcc-88aa-5d7da344ccd9",
        "task_uuid": "eff48172-2e75-4229-aff9-6c5d658db248",
        "task_type": "query",
        "is_successful": true,
        "duration": 105,
        "output": "W3siYW1vdW50IjoyOTkuNzYsImNyZWF0ZWRfYXQiOiIyMDIyLTA5LTMwIDE4OjUzOjM1IiwiY3VycmVuY3kiOiJFVVIiLCJjdXN0b21lcl9mcm9tX2lkIjoxLCJjdXN0b21lcl90b19pZCI6MiwiaWQiOjEsInVwZGF0ZWRfYXQiOiIyMDIyLTA5LTMwIDE4OjUzOjM1In0seyJhbW91bnQiOjExLjAxLCJjcmVhdGVkX2F0IjoiMjAyMi0wOS0zMCAxODo1NzozNSIsImN1cnJlbmN5IjoiRVVSIiwiY3VzdG9tZXJfZnJvbV9pZCI6MSwiY3VzdG9tZXJfdG9faWQiOjIsImlkIjoyLCJ1cGRhdGVkX2F0IjoiMjAyMi0wOS0zMCAxODo1MzozNSJ9LHsiYW1vdW50IjoxMS4wMSwiY3JlYXRlZF9hdCI6IjIwMjItMDktMzAgMTg6NTM6MzUiLCJjdXJyZW5jeSI6IkVVUiIsImN1c3RvbWVyX2Zyb21faWQiOjEsImN1c3RvbWVyX3RvX2lkIjoyLCJpZCI6MywidXBkYXRlZF9hdCI6IjIwMjItMDktMzAgMTg6NTM6MzUifSx7ImFtb3VudCI6MTMwMCwiY3JlYXRlZF9hdCI6IjIwMjItMDktMzAgMTg6NTQ6MjYiLCJjdXJyZW5jeSI6IlVTRCIsImN1c3RvbWVyX2Zyb21faWQiOjMsImN1c3RvbWVyX3RvX2lkIjo1LCJpZCI6NCwidXBkYXRlZF9hdCI6IjIwMjItMDktMzAgMTg6NTQ6MjYifSx7ImFtb3VudCI6MTMwMCwiY3JlYXRlZF9hdCI6IjIwMjItMDktMzAgMTg6NTQ6MjYiLCJjdXJyZW5jeSI6IlVTRCIsImN1c3RvbWVyX2Zyb21faWQiOjMsImN1c3RvbWVyX3RvX2lkIjo1LCJpZCI6NSwidXBkYXRlZF9hdCI6IjIwMjItMDktMzAgMTg6NTQ6MjYifSx7ImFtb3VudCI6MTUwNC4zNiwiY3JlYXRlZF9hdCI6IjIwMjItMDktMzAgMTg6NTQ6MzkiLCJjdXJyZW5jeSI6IlVTRCIsImN1c3RvbWVyX2Zyb21faWQiOjUsImN1c3RvbWVyX3RvX2lkIjozLCJpZCI6NiwidXBkYXRlZF9hdCI6IjIwMjItMDktMzAgMTg6NTQ6MzkifSx7ImFtb3VudCI6MzQuODksImNyZWF0ZWRfYXQiOiIyMDIyLTA5LTMwIDE4OjU1OjEwIiwiY3VycmVuY3kiOiJFVVIiLCJjdXN0b21lcl9mcm9tX2lkIjo0LCJjdXN0b21lcl90b19pZCI6MSwiaWQiOjcsInVwZGF0ZWRfYXQiOiIyMDIyLTA5LTMwIDE4OjU1OjEwIn0seyJhbW91bnQiOjU2NC44OSwiY3JlYXRlZF9hdCI6IjIwMjItMDktMzAgMTg6NTU6MjgiLCJjdXJyZW5jeSI6IkVVUiIsImN1c3RvbWVyX2Zyb21faWQiOjEsImN1c3RvbWVyX3RvX2lkIjo0LCJpZCI6OCwidXBkYXRlZF9hdCI6IjIwMjItMDktMzAgMTg6NTU6MjgifSx7ImFtb3VudCI6MTU2Ny41MSwiY3JlYXRlZF9hdCI6IjIwMjItMDktMzAgMTg6NTU6MjgiLCJjdXJyZW5jeSI6IkVVUiIsImN1c3RvbWVyX2Zyb21faWQiOjEsImN1c3RvbWVyX3RvX2lkIjo0LCJpZCI6OSwidXBkYXRlZF9hdCI6IjIwMjItMDktMzAgMTg6NTU6MjgifSx7ImFtb3VudCI6MjEuMTEsImNyZWF0ZWRfYXQiOiIyMDIyLTA5LTMwIDE4OjU2OjA2IiwiY3VycmVuY3kiOiJFVVIiLCJjdXN0b21lcl9mcm9tX2lkIjoyLCJjdXN0b21lcl90b19pZCI6MSwiaWQiOjEwLCJ1cGRhdGVkX2F0IjoiMjAyMi0wOS0zMCAxODo1NjowNiJ9LHsiYW1vdW50IjozNC4zNSwiY3JlYXRlZF9hdCI6IjIwMjItMDktMzAgMTg6NTY6MjYiLCJjdXJyZW5jeSI6IlVTRCIsImN1c3RvbWVyX2Zyb21faWQiOjMsImN1c3RvbWVyX3RvX2lkIjo1LCJpZCI6MTEsInVwZGF0ZWRfYXQiOiIyMDIyLTA5LTMwIDE4OjU2OjI2In0seyJhbW91bnQiOjExMi41NiwiY3JlYXRlZF9hdCI6IjIwMjItMDktMzAgMTg6NTY6NDQiLCJjdXJyZW5jeSI6IlVTRCIsImN1c3RvbWVyX2Zyb21faWQiOjUsImN1c3RvbWVyX3RvX2lkIjozLCJpZCI6MTIsInVwZGF0ZWRfYXQiOiIyMDIyLTA5LTMwIDE4OjU2OjQ0In1d",
        "metric_value": 0,
        "executed_at": "2024-03-22T12:57:49Z"
    },
    {
        "workflow_run_uuid": "746a0443-e3ff-4350-af4b-c7ac01b05acd",
        "task_uuid": "eff48172-2e75-4229-aff9-6c5d658db248",
        "task_type": "query",
        "is_successful": false,
        "duration": 1245,
        "output": "+iIYz/dFRiOhzfOmibIOxQ==",
        "metric_value": 0,
        "executed_at": "2024-03-22T12:57:02Z"
    },
    {
        "workflow_run_uuid": "5f96ec22-6b1c-42a4-a43c-bbb49b920937",
        "task_uuid": "eff48172-2e75-4229-aff9-6c5d658db248",
        "task_type": "query",
        "is_successful": false,
        "duration": 294,
        "output": "",
        "metric_value": 0,
        "executed_at": "2024-03-22T12:56:38Z"
    },
]
```

**Formatting notice**\
The "Output" field in the response in Base64 is encrypted and needs to be decrypted on the API client side.

## Get consolidated statistics of runs for pipelines and tasks

**Endpoint**

{% code overflow="wrap" %}
```
GET https://api.datamin.io/v1/stats/tasks/%%UUID%%/stats/%%DATE_TIME_FROM%%/%%DATE_TIME_TO%%
```
{% endcode %}

and

**Endpoint**&#x20;

{% code overflow="wrap" %}
```markup
GET https://api.datamin.io/v1/stats/pipelines/%%UUID%%/stats/%%DATE_TIME_FROM%%/%%DATE_TIME_TO%%
```
{% endcode %}

**Formatting notice**\
DATE\_TIME\_FROM and DATE\_TIME\_TO must be in the format "Y-m-d H:i:s". For example, "2024-01-01 14:23:01"

**Request body**\
empty\
\
**Authorization**\
Bearer: %%ACCESS\_TOKEN%%\
\
**Response example**

```
{
  "num_of_successes": int, 
  "num_of_failures": int, 
  "average_duration": int (e.g. in milliseconds), 
  "is_last_run_successful": bool, 
  "last_run_executed_at": datetime, 
  "last_run_duration": int (e.g. in milliseconds)
}
```

## Get aggregated statistics of runs for pipelines and tasks for the period of time

**Endpoint**

{% code overflow="wrap" %}
```
GET https://api.datamin.io/v1/stats/tasks/%%UUID%%/aggregated-stats/%%DATE_FROM%%/%%PERIOD%%/%%NUMBER_OF_PERIODS%%
```
{% endcode %}

and

**Endpoint**

{% code overflow="wrap" %}
```
GET https://api.datamin.io/v1/stats/pipelines/%%UUID%%/aggregated-stats/%%DATE_FROM%%/%%PERIOD%%/%%NUMBER_OF_PERIODS%%
```
{% endcode %}

%%PERIOD%% here has five possible values: day, week, month, quarter, year.

**Request example**\
GET /tasks/%%UUID%%/aggregated-stats/2020-01-01/month/12 will return a JSON array with 12 (or less if some don’t exist) elements each of which represents an aggregated statistic for a month starting on 2020-01-01.

**Request body**\
empty\
\
**Authorization**\
Bearer: %%ACCESS\_TOKEN%%\
\
**Response example**

```
{[
  {
    "date_from": string, 
    "date_to": string, 
    "num_of_successes": int, 
    "num_of_failures": int, 
    "average_duration": int (e.g. in milliseconds),
  }, 
  {
    "date_from": string, 
    "date_to": string, 
    "num_of_successes": int, 
    "num_of_failures": int, 
    "average_duration": int (e.g. in milliseconds),
  },
  {
    "date_from": string,
    "date_to": string, 
    "num_of_successes": int,
    "num_of_failures": int,
    "average_duration": int (e.g. in milliseconds),
  }, 
  ...
]}
```

## Get statistics of the last run for pipelines and tasks

**Endpoint**

{% code overflow="wrap" %}
```
GET https://api.datamin.io/v1/stats/tasks/%%UUID%%/last-run/stats
```
{% endcode %}

and

**Endpoint**

{% code overflow="wrap" %}
```
GET https://api.datamin.io/v1/stats/pipelines/%%UUID%%/last-run/stats
```
{% endcode %}

**Request body**\
empty\
\
**Authorization**\
Bearer: %%access\_token%%\
\
**Response example**

```
{
  "is_successful": bool, 
  "executed_at": datetime,
  "duration": int (e.g. in milliseconds),
}
```

