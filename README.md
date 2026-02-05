# 🚀 Microservices Demo Project

## 📌 Overview

This repository contains a **Spring Boot Microservices Demo Project** that demonstrates how multiple independent services communicate using **Eureka Service Discovery**. The project follows clean architecture principles and showcases real-world microservice patterns such as service registration, RESTful communication, and independent deployment.

The system is intentionally kept simple and beginner-friendly while still reflecting industry-standard microservices practices.

---

## 🧩 Services Included

### 1️⃣ Discovery Service (Eureka Server)

* Acts as a **service registry**
* Keeps track of all running microservices
* Enables service-to-service communication using service names instead of hardcoded URLs

### 2️⃣ User Service

* Manages **user-related operations**
* Exposes REST APIs for creating and retrieving users
* Registers itself with the Eureka Server

### 3️⃣ Task Service

* Manages **task-related operations**
* Supports CRUD operations on tasks
* Fetches user-related data using service discovery
* Registers itself with the Eureka Server

---

## 🏗️ Project Structure

```
MicroservicesDemoProject
│
├── discoveryservice
│   ├── application.properties
│   └── DiscoveryServiceApplication.java
│
├── userservice
│   ├── controller
│   ├── service
│   ├── repository
│   ├── model
│   ├── dto
│   ├── application.properties
│   └── UserServiceApplication.java
│
├── taskservice
│   ├── controller
│   ├── service
│   ├── repository
│   ├── model
│   ├── dto
│   ├── client
│   ├── exception
│   ├── application.properties
│   └── TaskServiceApplication.java
│
```

---

## 🧠 Architecture Overview

* Each microservice runs **independently** on its own port
* All services **register with Eureka Server** at startup
* Services discover each other dynamically using Eureka
* No hardcoded service URLs are used
* Each service can be scaled independently

```
[ User Service ]        [ Task Service ]
        ↓                      ↓
        └────── Eureka Discovery Server ──────┘
```

---

## ⚙️ Technology Stack

* Java
* Spring Boot
* Spring Cloud Netflix Eureka
* Spring Web (REST APIs)
* Spring Data JPA
* MySQL
* Maven

---

## ▶️ How to Run the Project

### Step 1: Start Discovery Service

* Run `DiscoveryServiceApplication`
* Access Eureka Dashboard:

  ```
  http://localhost:8761
  ```

### Step 2: Start User Service

* Run `UserServiceApplication`
* Verify registration in Eureka dashboard

### Step 3: Start Task Service

* Run `TaskServiceApplication`
* Verify registration in Eureka dashboard

---

## 🔗 API Endpoints Overview

### User Service

* `GET /api/users`
* `GET /api/users/{id}`
* `POST /api/users`

### Task Service

* `GET /api/tasks`
* `GET /api/tasks/{id}`
* `GET /api/tasks/assignee/{userId}`
* `POST /api/tasks`
* `PUT /api/tasks/{id}`
* `DELETE /api/tasks/{id}`

---

## ✅ Key Highlights

* Clean and modular microservice design
* Service discovery using Eureka
* RESTful APIs with proper separation of concerns
* Easy to understand project structure
* Suitable for beginners learning microservices

---

## 🏁 Conclusion

This project provides a **clear and practical introduction to microservices architecture using Spring Boot and Eureka**. It demonstrates how services can be developed, deployed, and scaled independently while communicating seamlessly through service discovery. The clean structure and modular approach make it ideal for learning, interviews, and showcasing microservices knowledge on GitHub.

