# User

```mermaid
erDiagram
    USER
    USER {
        uuid id PK
        varchar email UK
        varchar username
        varchar password "Hashed"
        timestamp created_at
        timestamp updated_at
    }
```