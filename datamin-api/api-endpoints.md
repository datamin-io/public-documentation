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

<figure><img src="../.gitbook/assets/Screenshot 2022-09-14 at 19.21.26.png" alt=""><figcaption></figcaption></figure>

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
