# todo

## Usage

1) Install dependency: ```npm install```
2) Create an ```.env``` file with the following fields
```json
ENVIRONMENT=dev

DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASSWORD=poostgres
DB_DATABASE=todo

PUBLIC_KEY="RSA PUBLIC KEY"
PRIVATE_KEY="RSA PRIVATE KEY"

JWT_SECRET="VERY SECRET"
MAX_USER_TOKEN_VALIDITY_SECONDS = 3600
```
3) Run migrations: ```npm run migration```
4) To run the server: ```npm run start```


## Endpoints

| Endpoints | Method | Description|
| --- | --- | --- |
| /api/todo/getAll | GET | Retrieves all todos |
| /api/todo/getUndone | GET | Retrieves all undone todos |
| /api/todo/getDone | GET | Retrieves all done todos |
| |
| /api/todo/createNew | POST | Creates a new todo |
| |
| /api/todo/get | GET | Retrives todo with the specified id |
| /api/todo/delete | DELETE | Delete todo with the specified id |
| /api/todo/markDone | PATCH | Mark todo with the specified id as done |
| /api/todo/markUndone | PATCH | Mark todo with the specified id as undone |
| /api/todo/update | PATCH | Updates description of todo with the specified id |

---

## API: /api/todo/getAll

### Description: 
Retrieves all todos

### Request body:
```json
{
    "data": {
        "todos": [
            {
                "id": 3,
                "task": "Your task goes here again",
                "done": false,
                "create_at": "2022-06-12T08:01:23.288Z",
                "updated_at": "2022-06-12T08:01:23.288Z"
            }
        ]
    }
}
```

### Reponse:
```json
{
    "data": [
        {
            "id": 7,
            "task": "hello",
            "done": false,
            "create_at": "2022-06-12T08:38:28.810Z",
            "updated_at": "2022-06-12T08:38:28.810Z"
        }
    ]
}
```

### Errors: 
None

---

## API: /api/todo/getUndone

### Description: 
Retrieves all undone todos

### Request body:
```json
{
    "data": {
        "todos": [
            {
                "id": 3,
                "task": "Your task goes here again",
                "done": false,
                "create_at": "2022-06-12T08:01:23.288Z",
                "updated_at": "2022-06-12T08:01:23.288Z"
            }
        ]
    }
}
```

### Reponse:

```json
{
    "data": [
        {
            "id": 7,
            "task": "hello",
            "done": false,
            "create_at": "2022-06-12T08:38:28.810Z",
            "updated_at": "2022-06-12T08:38:28.810Z"
        }
    ]
}
```

### Errors: 
None

---

## API: /api/todo/getDone

### Description: 
Retrieves all done todos

### Request body:
```json
{
    "data": [
        {
            "id": 7,
            "task": "hello",
            "done": true,
            "create_at": "2022-06-12T08:38:28.810Z",
            "updated_at": "2022-06-12T08:38:28.810Z"
        }
    ]
}
```

### Reponse:
Done todo as an array

### Errors: 
None

---

## API: /api/todo/createNew

### Description: 
Creates a new todo

### Request body:
```json
{
    "task": "Your task goes here"
}
```

### Reponse:
{
    "data": {
        "task": "Your task goes here again",
        "id": 14,
        "done": false,
        "create_at": "2022-06-12T10:37:03.008Z",
        "updated_at": "2022-06-12T10:37:03.008Z"
    }
}

### Errors: 
None

---

## API: /api/todo/get

### Description: 
Retrives todo with the specified id

### Request body:
```json
{
    "id": "Task id goes here"
}
```

### Reponse:
{
    "data": {
        "id": 4,
        "task": "Updated task",
        "done": true,
        "create_at": "2022-06-12T08:08:37.361Z",
        "updated_at": "2022-06-12T08:08:37.361Z"
    }
}

### Errors: 
None

---

## API: /api/todo/delete

### Description: 
Delete todo with the specified id

### Request body:
```json
{
    "id": "Task id goes here"
}
```

### Reponse:
```json
{
    "message": "Deleted"
}
```

### Errors: 
None

---

## API: /api/todo/markDone

### Description: 
Mark todo with the specified id as done

### Request body:
```json
{
    "id": "Task id goes here"
}
```

### Reponse:
```json
{
    "data": {
        "id": 4,
        "task": "Your task goes here again too",
        "done": true,
        "create_at": "2022-06-12T08:08:37.361Z",
        "updated_at": "2022-06-12T08:08:37.361Z"
    }
}
```

### Errors: 
None

---

## API: /api/todo/markUndone

### Description: 
Mark todo with the specified id as undone

### Request body:
```json
{
    "id": "Task id goes here"
}
```

### Reponse:
```json
{
    "data": {
        "id": 4,
        "task": "Your task goes here again too",
        "done": false,
        "create_at": "2022-06-12T08:08:37.361Z",
        "updated_at": "2022-06-12T08:08:37.361Z"
    }
}
```

### Errors: 
None

---

## API: /api/todo/update

### Description: 
Updates description of todo with the specified id

### Request body:
```json
{
    "id": "Task id goes here",
    "task": "Updated task goes here"
}
```

### Reponse:
```json
{
    "data": {
        "id": 4,
        "task": "Your task goes here again too",
        "done": false,
        "create_at": "2022-06-12T08:08:37.361Z",
        "updated_at": "2022-06-12T08:08:37.361Z"
    }
}
```

### Errors: 
None

---
# todo
