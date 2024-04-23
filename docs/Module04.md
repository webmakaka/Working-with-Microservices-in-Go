# [Udemy, Trevor Sawler] Working with Microservices in Go [ENG, 2022]

<br/>

## 04. Building a Logger Service

<br/>

### 01. What we'll cover in this section

<br/>

### 02. Getting started with the Logger service

```
$ cd logger-service
$ go mod init log-service
```

<br/>

```
$ go get go.mongodb.org/mongo-driver/mongo
$ go get go.mongodb.org/mongo-driver/mongo/options
```

<br/>

### 03. Setting up the Logger data models

<br/>

### 04. Finishing up the Logger data models

<br/>

### 05. Setting up routes, handlers, helpers, and a web server in our logger-service

<br/>

```
$ go get github.com/go-chi/chi/v5
$ go get github.com/go-chi/chi/v5/middleware
$ go get github.com/go-chi/cors
```

<br/>

### 06. Adding MongoDB to our docker-compose.yml file

```
$ make down && make up
$ make start
```

<br/>

```
$ cd ../apps/logger-service/
$ go run ./cmd/api
```

<br/>

### 07. Add the logger-service to docker-compose.yml and the Makefile

```
$ make down && make up_build && make up
$ make start
```

<br/>

### 08. Adding a route and handler on the Broker to communicate with the logger service

<br/>

---

<br/>

**Marley**

Any questions in english: <a href="https://jsdev.org/chat/">Telegram Chat</a>  
Любые вопросы на русском: <a href="https://jsdev.ru/chat/">Телеграм чат</a>
