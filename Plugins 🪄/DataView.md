---
title: "{{title}}"
twitch_chat_coordinates:
  input:
    x: 1271
    y: 963
  button:
    x: 1543
    y: 1004
project:
  name: "{{project_name}}"
  description: "{{project_description}}"
  status: in progress
  tags:
    - "#project"
    - "#{{project_tag}}"
  start_date:
    "{ date }": 
  due_date: "{{due_date}}"
database:
  type: SQLite
  schema:
    tables:
      - name: users
        columns:
          - name: id
            type: integer
            primary_key: true
          - name: username
            type: varchar
            unique: true
          - name: email
            type: varchar
          - name: created_at
            type: datetime
      - name: messages
        columns:
          - name: id
            type: integer
            primary_key: true
          - name: user_id
            type: integer
            foreign_key: users(id)
          - name: content
            type: text
          - name: timestamp
            type: datetime
api_endpoints:
  - name: Get User Data
    method: GET
    url: /api/users/{{user_id}}
    description: Fetches user data by user ID
  - name: Post Message
    method: POST
    url: /api/messages
    description: Submits a new message to the database
notes: |
  - Remember to set up proper indexing for database tables to optimize query performance.
  - API endpoints should include error handling and input validation.
---
```dataviewjs
const dbSchema = dv.current().database.schema.tables;

dv.header(2, "Database Schema");

dbSchema.forEach(table => {
    dv.header(3, `Table: ${table.name}`);
    dv.table(["Column Name", "Type", "Primary Key", "Foreign Key"], 
    table.columns.map(col => [
        col.name, 
        col.type, 
        col.primary_key ? "Yes" : "No", 
        col.foreign_key ? col.foreign_key : "None"
    ]));
});
```

## API Queries

```dataviewjs

```