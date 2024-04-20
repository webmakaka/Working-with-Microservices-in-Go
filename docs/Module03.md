# [Udemy, Trevor Sawler] Working with Microservices in Go [ENG, 2022]

<br/>

## 03. Building an Authentication Service

<br/>

### 01. What we'll cover in this section

<br/>

### 02. Setting up a stub Authentication service

```
$ cd authentication-service
$ go mod init authentication
```

<br/>

```
$ go get github.com/go-chi/chi/v5
$ go get github.com/go-chi/chi/v5/middleware
$ go get github.com/go-chi/cors
```

<br/>

### 03. Creating and connecting to Postgres from the Authentication service

```
$ go get github.com/jackc/pgconn
$ go get github.com/jackc/pgx/v4
$ go get github.com/jackc/pgx/v4/stdlib
```

<br/>

### 04. A note about PostgreSQL

<br/>

### 05. Updating our docker-compose.yml for Postgres and the Authentication service

```
$ make up_build
$ make down
$ make up
```

<br/>

```
$ docker logs run-authentication-service-1
2024/04/20 19:06:34 Starting authentication service
2024/04/20 19:06:34 Postgres not yet ready ...
2024/04/20 19:06:34 Backing off for two seconds ....
2024/04/20 19:06:36 Connected to Postgres!
```

<br/>

### 06. Populating the Postgres database

<br/>

![Application](/img/pic-m03-img01.png)

<br/>

```
// Import Data in PostgreSQL
data/users.sql
```

<br/>

![Application](/img/pic-m03-img02.png)

<br/>

### 07. Adding a route and handler to accept JSON

<br/>

https://github.com/tsawler/toolbox/blob/main/tools.go

<br/>

### 08. Update the Broker for a standard JSON format, and connect to our Auth service

<br/>

### 09. Updating the front end to authenticate thorough the Broker and trying things out

```
$ make down && make up_build && make up
$ make start
```

<br/>

```
// POST
$ curl \
    --data '{
        "email": "admin@example.com",
        "password": "verysecret"
}' \
    --header "Content-Type: application/json" \
    --request POST \
    --url http://localhost:8082/authenticate \
    | jq
```

<br/>

```json
// RESPONSE
{
  "error": false,
  "message": "Logged in user admin@example.com",
  "data": {
    "id": 2,
    "email": "admin@example.com",
    "first_name": "Admin",
    "last_name": "User",
    "active": 1,
    "created_at": "2022-03-14T00:00:00Z",
    "updated_at": "2022-03-14T00:00:00Z"
  }
}
```

<br/>

```
// POST
$ curl \
    --data '{
    "action": "auth",
    "auth": {
        "email": "admin@example.com",
        "password": "verysecret"
    }
}' \
    --header "Content-Type: application/json" \
    --request POST \
    --url http://localhost:8081/handle \
    | jq
```

<br/>

```
$ docker logs run-authentication-service-1
```

<br/>

![Application](/img/pic-m03-img03.png)

<br/>

---

<br/>

**Marley**

Any questions in english: <a href="https://jsdev.org/chat/">Telegram Chat</a>  
Любые вопросы на русском: <a href="https://jsdev.ru/chat/">Телеграм чат</a>
