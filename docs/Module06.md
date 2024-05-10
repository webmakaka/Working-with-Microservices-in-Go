# [Udemy, Trevor Sawler] Working with Microservices in Go [ENG, 2022]

<br/>

## 06. Building a Listener service AMQP with RabbitMQ

<br/>

### 01. What we'll cover in this section

<br/>

### 02. Creating a stub Listener service

```
$ cd listener-service/
$ go mod init listener
```

<br/>

```
$ go get github.com/rabbitmq/amqp091-go
```

<br/>

### 03. Adding RabbitMQ to our docker-compose.yml

```
$ docker-compose up -d
```

<br/>

### 04. Connecting to RabbitMQ

```
$ go run main.go
2024/05/10 21:40:49 Connected to RabbitMQ!
```

<br/>

### 05. Writing functions to interact with RabbitMQ

<br/>

### 06. Adding a logEvent function to our Listener microservice

<br/>

### 07. Updating main.go to start the Listener function

```
$ go run .
2024/05/10 22:55:12 Connected to RabbitMQ!
2024/05/10 22:55:12 Listening for and consuming RabbitMQ messages ...
Wainting for message [Exchange, Queue] [logs_topic, amq.gen-tBFaOoNB4XXmaQW75KVFJg]
```

<br/>

### 08. Change the RabbitMQ server URL to the Docker address

<br/>

### 09. Creating a Docker image and updating the Makefile

```
$ make up_build
```

<br/>

### 10. Updating the broker to interact with RabbitMQ

```
$ cd broker-service/
$ go get github.com/rabbitmq/amqp091-go
```

<br/>

### 11. Writing logic to Emit events to RabbitMQ

<br/>

### 12. Adding a new function in the Broker to log items via RabbitMQ

```
$ make up_build
$ make start
```

<br/>

http://localhost:8080/

<br/>

![Application](/img/pic-m06-img01.png)

<br/>

```
// OK!
$ docker-compose exec mongo mongo "mongodb://admin:password@localhost:27017/logs?authSource=admin&readPreference=primary&directConnection=true&ssl=false" --quiet --eval "db.logs.find().pretty()"
```

<br/>

**response:**

```json
***
{
	"_id" : ObjectId("663e8f4ce8aff643548eb53c"),
	"name" : "event",
	"data" : "Some kind of data",
	"created_at" : ISODate("2024-05-10T21:19:08.452Z"),
	"updated_at" : ISODate("2024-05-10T21:19:08.452Z")
}
```

<br/>

---

<br/>

**Marley**

Any questions in english: <a href="https://jsdev.org/chat/">Telegram Chat</a>  
Любые вопросы на русском: <a href="https://jsdev.ru/chat/">Телеграм чат</a>
