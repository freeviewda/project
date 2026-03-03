erDiagram
    USERS ||--o| PROFILES : "has (1:1)"
    USERS ||--o{ POSTS : "writes (1:N)"
    USERS ||--o{ COMMENTS : "writes (1:N)"
    USERS ||--o{ ENROLLMENTS : "takes (1:N)"
    USERS ||--o{ TEACHING_ASSIGNMENTS : "teaches (1:N)"
    
    POSTS ||--o{ COMMENTS : "contains (1:N)"
    
    COURSES ||--o{ ENROLLMENTS : "has students (1:N)"
    COURSES ||--o{ TEACHING_ASSIGNMENTS : "has teachers (1:N)"

    USERS {
        int id PK
        varchar name
        varchar email
    }
    PROFILES {
        int id PK
        int user_id FK
        text bio
    }
    POSTS {
        int id PK
        int user_id FK
        varchar title
    }
    COMMENTS {
        int id PK
        int post_id FK
        int user_id FK
    }
    COURSES {
        int id PK
        varchar name
        varchar code
    }
    ENROLLMENTS {
        int id PK
        int user_id FK
        int course_id FK
    }
    TEACHING_ASSIGNMENTS {
        int id PK
        int teacher_id FK
        int course_id FK
    }
    ATTACHMENTS {
        int id PK
        int attachable_id
        varchar attachable_type
    }
