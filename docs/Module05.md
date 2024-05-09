# [Udemy, Trevor Sawler] Working with Microservices in Go [ENG, 2022]

<br/>

## 05. Building a Mail Service

<br/>

### 01. What we'll cover in this section

<br/>

### 02. Adding Mailhog to our docker-compose.yml

```
$ make down && make up
```

<br/>

### 03. Setting up a stub Mail microservice

```
$ cd mail-service
$ go mod init mail-service
```

<br/>

```
$ go get github.com/go-chi/chi/v5
$ go get github.com/go-chi/chi/v5/middleware
$ go get github.com/go-chi/cors
```

<br/>

### 04. Building the logic to send email

<br/>

```
$ go get github.com/vanng822/go-premailer/premailer
$ go get github.com/xhit/go-simple-mail/v2
```

<br/>

### 05. Building the routes, handlers, and email templates

<br/>

### 06. Challenge Adding the Mail service to docker-compose.yml and the Makefile

<br/>

### 07. Solution to challenge

```
$ make up_build
```

<br/>

---

<br/>

**Marley**

Any questions in english: <a href="https://jsdev.org/chat/">Telegram Chat</a>  
Любые вопросы на русском: <a href="https://jsdev.ru/chat/">Телеграм чат</a>
