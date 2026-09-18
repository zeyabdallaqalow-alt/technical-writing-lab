,# Create a New Task

## Endpoint

*Method:* POST

*Path:* /api/v1/projects/{project_id}/tasks

## Description

Creates a new task in a project for an authenticated user.

## Path Parameters

| Name | Type | Required | Description |
|---|---|---|---|
| project_id | Integer | Yes | The unique ID of the project. |

## Request Body Parameters

| Name | Type | Required | Description |
|---|---|---|---|
| title | String | Yes | The title of the task. |
| description | String | No | Additional information about the task. |
| assignee_id | Integer | Yes | The ID of the assigned user. |
| due_date | String | Yes | The deadline in YYYY-MM-DD format. |
| priority | String | Yes | The priority: low, medium, or high. |

## Request Headers

| Header | Required | Description |
|---|---|---|
| Authorization | Yes | Authentication token. |
| Content-Type | Yes | Must be application/json. |

## Example Request

```json
{
  "title": "Complete Python assignment",
  "description": "Finish the Week 3 Python programming assignment.",
  "assignee_id": 27,
  "due_date": "2026-09-25",
  "priority": "high"
}Response Codes

Code — Explanation

201 Created — The task was successfully created.
400 Bad Request — Invalid or missing data.
401 Unauthorized — Authentication is missing or invalid.
403 Forbidden — The user does not have permission.
404 Not Found — The project or assignee does not exist.
409 Conflict — The request conflicts with the project state.
422 Unprocessable Entity — The submitted values fail validation.
500 Internal Server Error — An unexpected server error occurred.
{
  "id": 782,
  "project_id": 105,
  "title": "Complete Python assignment",
  "description": "Finish the Week 3 Python programming assignment.",
  "assignee_id": 27,
  "due_date": "2026-09-25",
  "priority": "high",
  "status": "open",
  "created_at": "2026-09-18T11:45:00Z"
}
