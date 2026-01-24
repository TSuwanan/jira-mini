# ER-Diagram: Jira Mini

## Database Schema

```mermaid
erDiagram
    roles {
        SERIAL id PK
        VARCHAR name UK "admin, user"
        TIMESTAMP created_at
        TIMESTAMP updated_at
    }

    users {
        UUID id PK
        VARCHAR user_code UK "LCB0001, LCB0002..."
        VARCHAR email UK
        VARCHAR password_hash
        VARCHAR full_name
        INTEGER role_id FK
        VARCHAR position_code "DEV, QA, PM, DES"
        VARCHAR level_code "S, M, J, L"
        TIMESTAMP created_at
        TIMESTAMP updated_at
        TIMESTAMP deleted_at
    }

    projects {
        UUID id PK
        VARCHAR project_code UK "PJ250122001..."
        VARCHAR name
        TEXT description
        INTEGER task_count
        UUID owner_id FK
        TIMESTAMP created_at
        TIMESTAMP updated_at
        TIMESTAMP deleted_at
    }

    project_members {
        UUID project_id PK,FK
        UUID user_id PK,FK
    }

    tasks {
        UUID id PK
        VARCHAR task_code UK "TSK250122001..."
        UUID project_id FK
        VARCHAR title
        TEXT description
        VARCHAR status "T, I, D"
        VARCHAR priority "L, M, H"
        UUID assignee_id FK
        UUID created_by FK
        DATE due_date
        TIMESTAMP created_at
        TIMESTAMP updated_at
        TIMESTAMP deleted_at
    }

    comments {
        UUID id PK
        UUID task_id FK
        UUID user_id FK
        TEXT content
        TIMESTAMP created_at
    }

    roles ||--o{ users : "has"
    users ||--o{ projects : "owns"
    users ||--o{ tasks : "assigned_to"
    users ||--o{ tasks : "created_by"
    users ||--o{ comments : "writes"
    users }o--o{ projects : "member_of"
    projects ||--o{ tasks : "contains"
    tasks ||--o{ comments : "has"
    project_members }o--|| projects : "belongs_to"
    project_members }o--|| users : "belongs_to"
```

## Tables Overview

| Table | Description |
|-------|-------------|
| **roles** | User roles (admin, user) |
| **users** | User accounts with position and level |
| **projects** | Projects with owner and task count |
| **project_members** | Many-to-many: Users assigned to Projects |
| **tasks** | Tasks with status, priority, and assignee |
| **comments** | Comments on tasks |

## Relationships

| From | To | Type | Description |
|------|-----|------|-------------|
| users | roles | Many-to-One | User has one role |
| projects | users | Many-to-One | Project has one owner |
| project_members | projects | Many-to-One | Junction table |
| project_members | users | Many-to-One | Junction table |
| tasks | projects | Many-to-One | Task belongs to project |
| tasks | users (assignee) | Many-to-One | Task assigned to user |
| tasks | users (created_by) | Many-to-One | Task created by user |
| comments | tasks | Many-to-One | Comment on task |
| comments | users | Many-to-One | Comment by user |

## Code Formats

| Entity | Format | Example |
|--------|--------|---------|
| User Code | `LCB` + 4 digits | LCB0001, LCB0002 |
| Project Code | `PJ` + YYMMDD + 3 digits | PJ250122001 |
| Task Code | `TSK` + YYMMDD + 3 digits | TSK250122001 |

## Status & Priority Codes

### Task Status
| Code | Description |
|------|-------------|
| T | Todo |
| I | In Progress |
| D | Done |

### Task Priority
| Code | Description |
|------|-------------|
| L | Low |
| M | Medium |
| H | High |

### Position Codes
| Code | Description |
|------|-------------|
| DEV | Developer |
| QA | Quality Assurance |
| PM | Project Manager |
| DES | Designer |

### Level Codes
| Code | Description |
|------|-------------|
| S | Senior |
| M | Middle |
| J | Junior |
| L | Lead |
