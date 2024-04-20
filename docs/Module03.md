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

![Application](/img/pic-m03-img01.png?raw=true)

<br/>

Import -> data/users.sql

<br/>

![Application](/img/pic-m03-img02.png?raw=true)

<br/>

---

<br/>

**Marley**

Any questions in english: <a href="https://jsdev.org/chat/">Telegram Chat</a>  
Любые вопросы на русском: <a href="https://jsdev.ru/chat/">Телеграм чат</a>
