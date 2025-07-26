# Context Apps MCP Tools Reference

Complete documentation for all available MCP tools in the Context Apps server.

## Overview

The Context Apps MCP server provides 18 tools across 4 productivity categories:
- **Todo**: 5 tools for task management
- **Idea**: 4 tools for idea management
- **Journal**: 5 tools for journaling with emotion tracking
- **Timer**: 4 tools for time tracking

Each tool requires the corresponding iOS app to be installed and authenticated with the same Apple ID.

## Authentication Flow

1. User connects MCP server in their client
2. Apple ID OAuth 2.0 authentication
3. Permission grants for app data access
4. Tools become available based on installed apps

---

## Task Management Tools

*Requires: [Context Todo](https://apps.apple.com/jp/app/context-todo-mcp%E5%AF%BE%E5%BF%9Ctodo%E3%82%A2%E3%83%97%E3%83%AA/id6747934261)*

### `todo_search`
Search todos by keyword.

**Parameters:**
```json
{
  "keyword": "string (optional) - Search keyword for partial title match"
}
```

**Example:**
```json
{
  "keyword": "presentation"
}
```

**Response:**
```json
{
  "content": [{
    "type": "text",
    "text": "JSON string of search results"
  }],
  "structuredContent": {
    "todos": [
      {
        "id": "uuid",
        "title": "Prepare Q4 presentation",
        "status": "pending",
        "created_at": "2024-01-10T14:30:00Z",
        "updated_at": "2024-01-10T14:30:00Z"
      }
    ]
  }
}
```

### `todo_insert`
Create a new todo. Available statuses can be retrieved with todo_status_list.

**Parameters:**
```json
{
  "title": "string (required) - Todo title (min 1 character)",
  "status": "string (required) - One of: pending, inProgress, completed"
}
```

**Example:**
```json
{
  "title": "Review quarterly report",
  "status": "pending"
}
```

### `todo_update`
Update an existing todo. Available statuses can be retrieved with todo_status_list.

**Parameters:**
```json
{
  "id": "string (required) - UUID of the todo to update",
  "title": "string (required) - New title (min 1 character)",
  "status": "string (required) - One of: pending, inProgress, completed"
}
```

### `todo_delete`
Delete a todo (logical deletion).

**Parameters:**
```json
{
  "id": "string (required) - UUID of the todo to delete"
}
```

### `todo_status_list`
Get list of todo statuses.

**Parameters:**
```json
{}
```

**Response:**
```json
{
  "structuredContent": {
    "statuses": [
      { "value": "pending", "label": "Pending" },
      { "value": "inProgress", "label": "In Progress" },
      { "value": "completed", "label": "Completed" }
    ]
  }
}
```

---

## Idea Management Tools

*Requires: [Context Idea](https://apps.apple.com/jp/app/context-idea-mcp%E5%AF%BE%E5%BF%9C%E3%82%A2%E3%82%A4%E3%83%87%E3%82%A2%E3%83%8E%E3%83%BC%E3%83%88/id6747934378)*

### `idea_search`
Search idea notes by keyword.

**Parameters:**
```json
{
  "keyword": "string (optional) - Search keyword for partial content match"
}
```

### `idea_insert`
Create a new idea note.

**Parameters:**
```json
{
  "content": "string (required) - Idea content (min 1 character)"
}
```

**Example:**
```json
{
  "content": "AI-powered garden automation system that adjusts watering based on weather predictions"
}
```

### `idea_update`
Update an existing idea note.

**Parameters:**
```json
{
  "id": "string (required) - UUID of the idea to update",
  "content": "string (required) - New content (min 1 character)"
}
```

### `idea_delete`
Delete an idea note (logical deletion).

**Parameters:**
```json
{
  "id": "string (required) - UUID of the idea to delete"
}
```

---

## Journal Tools

*Requires: [Context Journal](https://apps.apple.com/jp/app/context-journal-mcp%E5%AF%BE%E5%BF%9C%E6%97%A5%E8%A8%98%E3%82%A2%E3%83%97%E3%83%AA/id6747934304)*

### `journal_search`
Search journal entries.

**Parameters:**
```json
{
  "keyword": "string (optional) - Search keyword for partial content match",
  "min_score": "integer (optional) - Minimum emotion score (1-100)",
  "max_score": "integer (optional) - Maximum emotion score (1-100)",
  "tag_list": "array (optional) - Array of tag names to filter by"
}
```

**Example:**
```json
{
  "keyword": "meeting",
  "min_score": 70,
  "tag_list": ["work", "productivity"]
}
```

### `journal_insert`
Create a new journal entry. Available tags can be retrieved with journal_tag_list.

**Parameters:**
```json
{
  "content": "string (required) - Journal entry content (min 1 character)",
  "score": "integer (required) - Emotion score (1-100)",
  "tag_list": "array (required) - Array of tag names"
}
```

**Example:**
```json
{
  "content": "Had a productive day at work. Completed the presentation and received positive feedback.",
  "score": 85,
  "tag_list": ["work", "productivity", "achievement"]
}
```

### `journal_update`
Update an existing journal entry. Available tags can be retrieved with journal_tag_list.

**Parameters:**
```json
{
  "id": "string (required) - UUID of the journal entry to update",
  "content": "string (required) - New content (min 1 character)",
  "score": "integer (required) - New emotion score (1-100)",
  "tag_list": "array (required) - New array of tag names"
}
```

### `journal_delete`
Delete a journal entry (logical deletion).

**Parameters:**
```json
{
  "id": "string (required) - UUID of the journal entry to delete"
}
```

### `journal_tag_list`
Get list of user's journal tags.

**Parameters:**
```json
{}
```

**Response:**
```json
{
  "structuredContent": {
    "tags": [
      { "id": "uuid", "name": "work", "usage_count": 25 },
      { "id": "uuid", "name": "productivity", "usage_count": 18 }
    ]
  }
}
```

---

## Time Management Tools

*Requires: [Context Timer](https://apps.apple.com/jp/app/context-timer-mcp%E5%AF%BE%E5%BF%9C%E3%82%BF%E3%82%A4%E3%83%9E%E3%83%BC/id6747934337)*

### `timer_search`
Search timer sessions.

**Parameters:**
```json
{
  "keyword": "string (optional) - Search keyword for partial task name match",
  "date": "string (optional) - Date in ISO 8601 format to find sessions containing this date",
  "min_duration": "integer (optional) - Minimum duration in seconds (min 0)",
  "max_duration": "integer (optional) - Maximum duration in seconds (min 0)"
}
```

**Example:**
```json
{
  "keyword": "coding",
  "date": "2024-01-15",
  "min_duration": 1800
}
```

### `timer_insert`
Create a new timer session.

**Parameters:**
```json
{
  "task_name": "string (required) - Task name (min 1 character)",
  "start_time": "string (required) - Start time in ISO 8601 format",
  "end_time": "string (required) - End time in ISO 8601 format (null for ongoing)",
  "duration": "integer (required) - Elapsed time in seconds (min 0)",
  "paused_duration": "integer (required) - Paused duration in seconds (min 0)",
  "is_paused": "boolean (required) - Whether the timer is paused",
  "last_resume_time": "string (required) - Last resume time in ISO 8601 format (null if not resumed)"
}
```

**Example:**
```json
{
  "task_name": "Code review for feature X",
  "start_time": "2024-01-15T09:00:00Z",
  "end_time": "2024-01-15T10:30:00Z",
  "duration": 5400,
  "paused_duration": 0,
  "is_paused": false,
  "last_resume_time": null
}
```

### `timer_update`
Update task name of an existing timer session.

**Parameters:**
```json
{
  "id": "string (required) - UUID of the timer session to update",
  "task_name": "string (required) - New task name (min 1 character)"
}
```

### `timer_delete`
Delete a timer session (logical deletion).

**Parameters:**
```json
{
  "id": "string (required) - UUID of the timer session to delete"
}
```

---

## Response Format

All tools return standardized JSON responses:

```json
{
  "content": [{
    "type": "text",
    "text": "JSON string representation of the response"
  }],
  "structuredContent": {
    // Tool-specific response data
  }
}
```

## Error Handling

Errors are thrown as exceptions with descriptive messages:

- `認証情報またはDBが利用できません` - Authentication or database not available
- `データが見つかりません` - Data not found
- `権限がありません` - Permission denied
- Various validation errors for invalid parameters

## Data Privacy & Security

* **User Isolation**: Each user can only access their own data
* **Logical Deletion**: Delete operations don't physically remove data
* **UUID Identifiers**: All resources use secure UUID identifiers
* **Authentication Required**: All operations require valid Apple ID authentication

## Best Practices

1. **Search before Create**: Use search tools to avoid duplicates
2. **Use Status/Tag Lists**: Call `todo_status_list` and `journal_tag_list` to get valid values
3. **ISO 8601 Dates**: All timestamps use ISO 8601 format
4. **Emotion Scores**: Journal scores range from 1 (very negative) to 100 (very positive)
5. **Timer Precision**: Timer durations are in seconds for precision

---

For additional support or questions, contact: support@basaapp.com