# [Udemy, Trevor Sawler] Working with Microservices in Go [ENG, 2022]

<br/>

## 07. Communicating between services using Remote Procedure Calls (RPC)

<br/>

### 01. What we'll cover in this section

<br/>

### 02. Setting up an RPC server in the Logger microservice

<br/>

### 03. Listening for RPC calls in the Logger microservice

<br/>

### 04. Calling the Logger from the Broker using RPC

<br/>

### 05. Trying things out

```
$ make up_build
$ make start
```

<br/>

http://localhost:8080/

<br/>

![Application](/img/pic-m07-img01.png)

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
	"_id" : ObjectId("663ff791b735d6aa900a590c"),
	"name" : "event",
	"data" : "Some kind of data",
	"created_at" : ISODate("2024-05-11T22:56:17.924Z"),
	"updated_at" : ISODate("0001-01-01T00:00:00Z")
}
```

<br/>

---

<br/>

**Marley**

Any questions in english: <a href="https://jsdev.org/chat/">Telegram Chat</a>  
Любые вопросы на русском: <a href="https://jsdev.ru/chat/">Телеграм чат</a>
