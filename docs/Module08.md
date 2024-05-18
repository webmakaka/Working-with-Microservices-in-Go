# [Udemy, Trevor Sawler] Working with Microservices in Go [ENG, 2022]

<br/>

## 08. Speeding things up (potentially) with gRPC

<br/>

### 01. What we'll cover in this section

<br/>

### 02. Installing the necessary tools for gRPC

```
$ go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.27
$ go install google.golang.org/grpc/cmd/protoc-gen-go@v1.2
```

```
$ go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest
```

<br/>

### 03. Defining a Protocol for gRPC the .proto file

<br/>

### 04. Generating the gRPC code from the command line

https://github.com/protocolbuffers/protobuf/releases

<br/>

protoc-26.1-linux-x86_64.zip

<br/>

```
$ cp protoc $GO_HOME/bin
```

<br/>

```
$ protoc --version
libprotoc 26.1
```

<br/>

```
$ cd apps/logger-service/logs/
$ protoc --go_out=. --go_opt=paths=source_relative --go-grpc_out=. --go-grpc_opt=paths=source_relative logs.proto
```

<br/>

### 05. Getting started with the gRPC server

```
$ cd apps/logger-service/
$ go get google.golang.org/grpc
$ go get google.golang.org/protobuf
```

<br/>

### 06. Listening for gRPC connections in the Logger microservice

<br/>

### 07. Writing the client code

```
$ cd apps/broker-service/
$ go get google.golang.org/grpc
```

<br/>

```
$ cd apps/broker-service/logs/
$ protoc --go_out=. --go_opt=paths=source_relative --go-grpc_out=. --go-grpc_opt=paths=source_relative logs.proto
```

<br/>

### 08. Updating the front end code

<br/>

### 09. Trying things out

<br/>

```
$ cd apps/logger-service
$ go mod tidy
```

<br/>

```
$ make up_build
$ make start
```

<br/>

http://localhost:8080/

<br/>

![Application](/img/pic-m08-img01.png)

<br/>

```
$ docker-compose exec mongo mongo "mongodb://admin:password@localhost:27017/logs?authSource=admin&readPreference=primary&directConnection=true&ssl=false" --quiet --eval "db.logs.find().pretty()"
```

<br/>

**response:**

```
***
{
	"_id" : ObjectId("664915c9ce1d0a5a43169cc6"),
	"name" : "event",
	"data" : "Some kind of gRPC data",
	"created_at" : ISODate("2024-05-18T20:55:37.493Z"),
	"updated_at" : ISODate("2024-05-18T20:55:37.493Z")
}
```

<br/>

---

<br/>

**Marley**

Any questions in english: <a href="https://jsdev.org/chat/">Telegram Chat</a>  
Любые вопросы на русском: <a href="https://jsdev.ru/chat/">Телеграм чат</a>
