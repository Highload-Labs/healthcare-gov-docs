# User

```mermaid
erDiagram
    USER
    USER {
        uuid id PK
        string email UK
        string username
        string password "Hashed"
        timestamp created_at
        timestamp updated_at
    }
```