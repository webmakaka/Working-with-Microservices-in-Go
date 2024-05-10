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

---

<br/>

**Marley**

Any questions in english: <a href="https://jsdev.org/chat/">Telegram Chat</a>  
Любые вопросы на русском: <a href="https://jsdev.ru/chat/">Телеграм чат</a>
