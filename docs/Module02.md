# [Udemy, Trevor Sawler] Working with Microservices in Go [ENG, 2022]

<br/>

## 02. Building a simple front end and one Microservice

<br/>

### 03. Reviewing the front end code

```
$ cd apps/front-end
$ go run ./cmd/web
```

<br/>

```
http://localhost:8080/
```

<br/>

![Application](/img/pic-m02-img01.png?raw=true)

<br/>

### 04. Our first service the Broker

```
$ cd apps/broker-service
$ go mod init broker

$ go get github.com/go-chi/chi/v5
$ go get github.com/go-chi/chi/v5/middleware
$ go get github.com/go-chi/cors
```

```
$ go run ./cmd/api/
```

<br/>

### 05. Building a docker image for the Broker service

```
$ cd docker/
$ docker-compose up -d
```

<br/>

### 06. Adding a button and JavaScript to the front end

<br/>

```
// POST
$ curl \
    --data '{}' \
    --header "Content-Type: application/json" \
    --request POST \
    --url http://localhost:8081/ \
    | jq
```

<br/>

```json
{
  "error": false,
  "message": "Hit the broker"
}
```

<br/>

```
$ cd apps/front-end
$ go run ./cmd/web
```

<br/>

![Application](/img/pic-m02-img02.png?raw=true)

<br/>

### 07. Creating some helper functions to deal with JSON and such

<br/>

---

<br/>

**Marley**

Any questions in english: <a href="https://jsdev.org/chat/">Telegram Chat</a>  
Любые вопросы на русском: <a href="https://jsdev.ru/chat/">Телеграм чат</a>
