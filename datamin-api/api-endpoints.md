# API Endpoints

As soon as you created your first [OAuth client](oauth-clients.md) and saved its client secret you can start integrating Datamin with your application via API.

Currently the following API endpoints are available:

## Generate OAuth2 token

**Endpoint:**\
\[GET/POST] https://api.datamin.io/v1/oauth/token?client\_id=%%CLIENT\_ID%%\&client\_secret=%%CLIENT\_SECRET%%\&grant\_type=client\_credentials\
\
**Request body:**\
empty\
\
**Response example:**

```json
{
  "access_token": "ZJG5NZFLOWUTYJYWYY0ZOGU3LWI5NZMTYMJLZTJHZJAYNWNJ",
  "expires_in": 86400,
  "refresh_token": "ODQZYTQ2ZMUTOWNHZC01NDG2LWI1ZDMTNZM5YJY1ZWJJZTCW",
  "scope": "workflows:run",
  "token_type": "Bearer"
}
```

## Run workflow

Workflow UUID can be found in the list of workflows:

<div align="center">

<figure><img src="../.gitbook/assets/Screenshot 2022-09-14 at 19.21.26.png" alt=""><figcaption></figcaption></figure>

</div>

**Endpoint:**\
POST https://api.datamin.io/v1/workflows/%%WORKFLOW\_UUID%%/runs/\
\
**Request body:**\
empty\
\
**Authorization:**\
Bearer: %%access\_token%%\
\
**Response example:**

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

## Get various statistics of runs for workflows and separate tasks

**Endpoint**\
GET https://api.datamin.io/v1/stats/tasks/%%UUID%%/stats/%%DATE\_FROM%%/%%DATE\_TO%%

and

**Endpoint** \
GET https://api.datamin.io/v1/stats/workflows/%%UUID%%/stats/%%DATE\_FROM%%/%%DATE\_TO%%

**Request body:**\
empty\
\
**Authorization:**\
Bearer: %%access\_token%%\
\
**Response example:**

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

**Endpoint:** \
GET https://api.datamin.io/v1/stats/tasks/%%UUID%%/aggregated-stats/%%DATE\_FROM%%/%%PERIOD%%/%%NUMBER\_OF\_PERIODS%%

and

**Endpoint:** \
GET https://api.datamin.io/v1/stats/workflows/%%UUID%%/aggregated-stats/%%DATE\_FROM%%/%%PERIOD%%/%%NUMBER\_OF\_PERIODS%%

%%PERIOD%% here has five possible values: day, week, month, quarter, year.

E.g. GET /tasks/%%UUID%%/aggregated-stats/2020-01-01/month/12 will return a JSON array with 12 (or less if some don’t exist) elements each of which represent an aggregated statistic for a month period of time starting on 2020-01-01.

**Request body:**\
empty\
\
**Authorization:**\
Bearer: %%access\_token%%\
\
**Response example:**

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

**Endpoint:** \
GET https://api.datamin.io/v1/stats/tasks/%%UUID%%/last-run/stats

and

**Endpoint:** \
GET https://api.datamin.io/v1/stats/workflows/%%UUID%%/last-run/stats

**Request body:**\
empty\
\
**Authorization:**\
Bearer: %%access\_token%%\
\
**Response example:**

```
{
  "is_successful": bool, 
  "executed_at": datetime,
  "duration": int (e.g. in milliseconds),
}
```

