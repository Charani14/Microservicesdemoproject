🚀 Microservice Demo Project
📖 Overview

This project demonstrates a Spring Boot–based Microservices Architecture using Eureka Service Discovery.
It showcases how multiple independent services can register, discover, and interact within a distributed system.

The application is designed as a simple Task Management System with separate services for users and tasks.

🏗 Architecture Overview

The project follows a service-oriented architecture, where each service runs independently and communicates through service discovery.

MicroserviceDemoProject
│
├── discoveryservice   (Eureka Server)
├── userservice        (User Management)
└── taskservice        (Task Management)

🧩 Microservices Description
1️⃣ Discovery Service (Eureka Server)

Purpose:
Acts as a centralized Service Registry where all microservices register themselves and discover other services dynamically.

Responsibilities:

Registers all microservices

Enables service-to-service discovery

Monitors service health

Provides a web-based dashboard

Port:

8761


Dashboard URL:

http://localhost:8761

2️⃣ User Service

Purpose:
Manages all user-related operations and persists user data.

Responsibilities:

Create users

Fetch users

Store user details in database

Register with Eureka automatically

Port:

8081

API Endpoints
HTTP Method	Endpoint	Description
POST	/api/users	Create a new user
GET	/api/users	Fetch all users
GET	/api/users/{id}	Fetch user by ID
3️⃣ Task Service

Purpose:
Manages task-related operations and associates tasks with users.

Responsibilities:

Create tasks

Update task details

Delete tasks

Assign tasks to users

Fetch tasks by user

Register with Eureka automatically

Port:

8080

API Endpoints
HTTP Method	Endpoint	Description
GET	/api/tasks	Fetch all tasks
GET	/api/tasks/{id}	Fetch task by ID
GET	/api/tasks/assignee/{userId}	Fetch tasks by user
POST	/api/tasks	Create a task
PUT	/api/tasks/{id}	Update a task
DELETE	/api/tasks/{id}	Delete a task
⚙️ Technologies Used

Java 17+

Spring Boot

Spring Cloud Netflix Eureka

Spring Data JPA

MySQL

RESTful APIs

Maven

Jakarta Validation

🗄 Database Configuration

Create the following MySQL databases:

userservice_db
taskservice_db


Update database credentials in each service’s application.properties.

▶️ How to Run the Application
Step 1: Clone the Repository
git clone <repository-url>
cd microservicedemoproject

Step 2: Start Discovery Service
cd discoveryservice
mvn spring-boot:run


Verify:

http://localhost:8761

Step 3: Start User Service
cd userservice
mvn spring-boot:run

Step 4: Start Task Service
cd taskservice
mvn spring-boot:run

🔍 Service Registration Verification

Open the Eureka dashboard:

http://localhost:8761


You should see:

USERSERVICE → UP

TASKSERVICE → UP

🧪 API Testing

APIs can be tested using:

Postman

Browser (GET requests)

Swagger UI (if configured)

📂 Project Structure (Per Service)
controller   → REST endpoints
service      → Business logic
repository   → Database interaction
entity/model → JPA entities
dto          → Request and response objects

⭐ Key Concepts Demonstrated

Microservices Architecture

Service Discovery using Eureka

Loose coupling between services

RESTful API design

DTO-based request/response handling

Database integration with JPA

Validation using Jakarta Validation

🔮 Future Enhancements

API Gateway integration

Feign Client for inter-service communication

Centralized logging

Circuit breaker implementation

Docker & Docker Compose

CI/CD pipeline integration

✅ Conclusion

This project provides a clear demonstration of Spring Boot microservices using Eureka Service Discovery.
It highlights how independent services can be developed, registered, and managed efficiently while maintaining scalability and loose coupling.
The architecture follows industry best practices and serves as a solid foundation for building real-world distributed systems.
