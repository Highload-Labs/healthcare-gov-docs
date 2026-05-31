# Enrollment

```mermaid
erDiagram
    ENROLLMENT
    ENROLLMENT {
        uuid id PK
        uuid user_id FK
        uuid plan_id FK
        timestamp effective_date
        timestamp end_date
        timestamp created_at
        timestamp updated_at
    }
```