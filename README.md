# 📅 Week 1: Master the Core Development Workflow
Goal: Improve efficiency in writing, debugging, and testing code.

## Day 1-2: Java Core Enhancements

### Goals
- Review Java 8+ features (Streams, Lambdas, Optional) → Code small examples.
- Practice Multithreading (Executors, CompletableFuture).
- Debug Java code using breakpoints & stack traces in IntelliJ.

### Tasks

- Implement Java 8+ features (Streams, Lambdas, Optional).
- Write a multithreaded program using Executors & CompletableFuture.
- Debug Java code using breakpoints & stack traces in IntelliJ.
### 🎯 Expected Output
✔️ Java programs demonstrating Streams, Optional, and CompletableFuture.
✔️ A multithreaded program that correctly handles tasks asynchronously.
✔️ Ability to debug stack traces and pinpoint errors.

### Assignments
- Create a list of 1000 random integers, filter items < 100, double them then sort asc, take the first 4 numbers
- Create a callable task that return a string, print the result from the main thread
- Create two mock apis that return strings or throw an error. Use completable future to create a joined string from the two results in the order of string 1 + string 2. In the case of exception, return an empty string for each task. Use `exceptionally`

```java
    public static String mockApi1() throws Exception {
        int sleepTime = random.nextInt(5) + 1; // 1 to 5 seconds
        TimeUnit.SECONDS.sleep(sleepTime);
        if (random.nextBoolean()) { // 50% chance to throw an exception
            throw new Exception("Mock API 1 failed");
        }
        return "String1";
    }

    public static String mockApi2() throws Exception {
        int sleepTime = random.nextInt(5) + 1; // 1 to 5 seconds
        TimeUnit.SECONDS.sleep(sleepTime);
        if (random.nextBoolean()) { // 50% chance to throw an exception
            throw new Exception("Mock API 2 failed");
        }
        return "String2";
    }

```

- 
## Day 3-4: REST API Development with Spring Boot
### Goals
- Build a simple CRUD API (Spring Boot, JPA, H2/PostgreSQL).
- Handle request validation (@Valid, @NotNull).
- Write unit tests with JUnit & Mockito.
- Test API using Postman (GET, POST, PUT, DELETE).

### Tasks

- Build a simple CRUD API (Spring Boot, JPA, H2/PostgreSQL).
- Implement request validation (@Valid, @NotNull).
- Write unit tests with JUnit & Mockito.
- Test API using Postman.

### 🎯 Expected Output
✔️ A working REST API with CRUD operations.
✔️ Validation logic properly rejecting invalid input.
✔️ Postman requests showing API responses.
✔️ Unit tests passing successfully.

### Assignments
- Create a CRUD API with spring mvc for a task management app
- User can login with user name and password
- user can add and remove tasks
- users cannot remove other people's tasks
- There is an admin role where user can remove all other users' tasks
- Have unit test for adding, removing tasks

## Day 5-6: Debugging & Logs
### Goals
- Add structured logging using SLF4J, Logback.
- Practice debugging API response issues.

### Tasks

- Add structured logging using SLF4J, Logback.
- Practice debugging API response issues.

### 🎯 Expected Output
✔️ Application logs showing structured request-response flow.
✔️ Debugging session where an issue is identified and fixed.
✔️ Hibernate query optimization reducing unnecessary DB calls.

### Assignment
- Create a new java project, add logback, slf4j for logging
- Set different log levels for different packages

## Day 7: Code Review & Best Practices
### Goals
- Read SOLID principles and apply them to your code. 
- Explore common design patterns (Factory, Singleton, Builder).
- Review your past PRs, find areas for improvement. [Optional]

### Tasks

- Read and apply SOLID principles.
- Refactor code to use common design patterns (Factory, Singleton, Builder).
- Review past PRs and note improvement points.

### 🎯 Expected Output
✔️ Refactored code applying SOLID principles.
✔️ Improved design using appropriate patterns.
✔️ Constructive feedback on past PRs.

### Assignments
- Read this article about SOLID: https://www.digitalocean.com/community/conceptual-articles/s-o-l-i-d-the-first-five-principles-of-object-oriented-design#interface-segregation-principle
- Create code using Builder, Singleton (thread safe), Builder, Proxy, Visitor patterns


# 📅 Week 2: Database & Performance Optimization
Goal: Learn to write efficient queries, avoid performance pitfalls, and optimize API response times.

## Day 8-9: SQL & JPA Mastery
### Goals
-  Write JOIN queries, Indexing, Transactions.
-  Learn Hibernate Lazy vs. Eager Loading.
-  Experiment with @Query, @Modifying, and EntityGraph.

### Tasks

- Write JOIN queries, Indexing, Transactions.
- Learn Hibernate Lazy vs. Eager Loading.
- Experiment with @Query, @Modifying, and EntityGraph.

### 🎯 Expected Output
✔️ Optimized SQL queries performing well.
✔️ Hibernate fetch strategy correctly fetching required data.
✔️ No unnecessary queries in API logs.

### Assigments
#### Using join
Create a relational schema in PostgreSQL with at least 3 tables:
```
users (id, name, email, role_id)
roles (id, name)
orders (id, user_id, total_amount, created_at)
```
Write JOIN queries:

- Fetch all users with their roles.
- Fetch users along with their total orders.
- Fetch users who have never placed an order.

####  Implement transactions correctly in Java with JPA
Create a Service Method in Spring Boot:

- Implement a method that transfers money between two users.
- Ensure ACID compliance using @Transactional.

Introduce a failure:

- Simulate a failure (e.g., throw an exception) in the middle of the transaction.
- Verify whether partial updates happen or if rollback works.
#### Understand Lazy vs. Eager Loading and prevent N+1 query problems.
Modify the Schema:

Use JPA to define User, Role, and Order entities.
Define relationships (@OneToMany, @ManyToOne).
Fetch Strategies Experiment:

Set @OneToMany(fetch = FetchType.LAZY) and observe queries.
Change to FetchType.EAGER and analyze the difference.
Detect & Fix N+1 Queries:

Check API logs for unnecessary queries.
Optimize using @EntityGraph.


## Day 10-11: Hibernate Performance & Caching
### Goals

-  Enable Hibernate SQL logging → Analyze generated queries.
-  Use Redis or Caffeine caching to optimize read performance.
-  Measure API response time with Spring Actuator & Postman.

🎯 Expected Output
✔️ Logs showing optimized Hibernate queries.
✔️ API responses using cache for faster access.
✔️ Spring Actuator displaying API response times.

## Day 12-13: Transactions & Error Handling
### Goals
-  Learn Propagation & Isolation levels in Spring Transactions.
-  Handle common transactional pitfalls (deadlocks, lost updates).
-  Improve error handling using @ControllerAdvice + Custom Exception Handling.

### Tasks

- Learn Propagation & Isolation levels in Spring Transactions.
- Handle transactional failures with retry mechanisms.
- Implement @ControllerAdvice for centralized error handling.

### 🎯 Expected Outputt
✔️ Application handling transaction failures gracefully.
✔️ Properly configured transaction isolation preventing data issues.
✔️ Centralized error-handling strategy in place.
### Tasks

- Enable Hibernate SQL logging.
- Implement Redis or Caffeine caching.
- Measure API response time with Spring Actuator.

### 🎯 Expected Output
✔️ Logs showing optimized Hibernate queries.
✔️ API responses using cache for faster access.
✔️ Spring Actuator displaying API response times.

## Day 14: Test, Refactor, and Improve Code [Optional]
### Goals
- Identify slow queries and optimize.
- Refactor API to improve database interactions.
- Write integration tests using TestContainers.
### Tasks

- Identify and optimize slow DB queries.
- Refactor API to improve database interactions.
- Write integration tests using TestContainers.

### 🎯 Expected Output
✔️ Database queries are optimized and fast.
✔️ Code refactored for better DB interaction.
✔️ Passing integration tests using TestContainers.

# 📅 Week 3: API Security & Deployment Best Practices
Goal: Secure APIs, understand CI/CD, and deploy apps efficiently.

## Day 15-16: API Security with Spring Security
### Goals
- Implement JWT Authentication (Spring Security + JWT).
- Add Role-Based Access Control (RBAC).
- Prevent common security threats (CORS, CSRF, SQL Injection).
### Tasks

- Implement JWT Authentication.
- Add Role-Based Access Control (RBAC).
- Prevent CORS, CSRF, SQL Injection vulnerabilities.

### 🎯 Expected Outputt
✔️ API secured with JWT Authentication.
✔️ Access properly restricted by user roles.
✔️ Security vulnerabilities mitigated.
## Day 17-18: CI/CD & Deployment Basics

### Goals
- Learn Maven vs. Gradle and build an executable JAR.
- Write a Dockerfile and containerize a Spring Boot app.
- Deploy app using Docker Compose.
### Tasks

- Build an executable JAR using Maven/Gradle.
- Write a Dockerfile and containerize the Spring Boot app.
- Deploy app using Docker Compose.

### 🎯 Expected Outputt
✔️ Working Docker container running the application.
✔️ Build and deployment scripts ready for CI/CD.
✔️ Automated deployment workflow.

## Day 19-20: Logging & Monitoring
### Goals
- Use Spring Boot Actuator for monitoring health/status.
- Set up centralized logging with ELK Stack (Elasticsearch, Logstash, Kibana).
- Learn API rate limiting (Spring Boot + Redis).

### Tasks

Use Spring Boot Actuator for monitoring.
Set up ELK Stack (Elasticsearch, Logstash, Kibana).
Implement API rate limiting using Redis.
### 🎯 Expected Outputt
✔️ API health monitoring via Spring Boot Actuator.
✔️ Logs centralized in ELK Stack.
✔️ Rate-limiting working correctly.

## Day 21: Improve API Performance & Load Testing [Optional]
### Goals
- Use JMeter to simulate 100+ requests per second.
- Tune JVM settings & connection pooling (HikariCP).
- Implement circuit breaker (Resilience4J, Hystrix) to handle failures.
### Tasks

Simulate 100+ requests per second using JMeter.
Tune JVM settings & connection pooling (HikariCP).
Implement circuit breaker (Resilience4J, Hystrix).
### 🎯 Expected Outputt
✔️ Performance metrics before & after optimization.
✔️ API can handle high loads efficiently.
✔️ Circuit breaker preventing system failures.
# 📅 Week 4: Advanced Topics & Hands-On Projects
Goal: Work on real-world problems, optimize existing skills, and build confidence.

## Day 22-23: Microservices & Messaging Basics
### Goals
- Explore Event-Driven Architecture with Kafka/RabbitMQ.
- Implement simple producer-consumer using Kafka.
### Tasks

Learn Event-Driven Architecture with Kafka/RabbitMQ.
Implement a simple producer-consumer using Kafka.
### 🎯 Expected Outputt
✔️ Kafka message producer and consumer running correctly.
✔️ Logs confirming message delivery between services.

## Day 24-25: Scaling & Distributed Systems [Optional]
### Goals 
- Learn Spring Cloud basics (Config Server, Service Discovery).
- Understand API Gateway & Load Balancing.
### Tasks

- Explore Spring Cloud basics (Config Server, Service Discovery).
- Implement API Gateway & Load Balancing.
### 🎯 Expected Outputt
✔️ Microservice communication via Service Discovery.
✔️ API Gateway routing traffic correctly.


## Day 26-27: Build a Full-Fledged API from Scratch
### Goals
- Use Spring Boot, PostgreSQL, Docker, and Redis.
- Implement authentication (JWT), caching (Redis), and pagination.
### Tasks

Use Spring Boot, PostgreSQL, Docker, and Redis.
Implement authentication (JWT), caching (Redis), and pagination.
### 🎯 Expected Outputt
✔️ A working end-to-end API with security & optimizations.
✔️ API properly handling large-scale requests.


## Day 28: Self-Assessment & Next Steps
### Goals
- Review past PRs & refactor old code.
- Write a blog post or documentation summarizing what you learned.
- Plan the next roadmap (e.g., GraphQL, Spring Cloud, Serverless).
### Tasks

Review past PRs & refactor old code.
Write a blog post or documentation summarizing the journey.
Plan next roadmap (e.g., GraphQL, Spring Cloud, Serverless).
### 🎯 Expected Outputt
✔️ Improved and optimized past code.
✔️ A blog post/documentation summarizing key learnings.
✔️ Clear roadmap for further learning.
