# System Architectural Styles

# Monolithic Architecture

Monolithic architecture is a traditional approach to software design where all the functionalities of an application are packaged together into a single executable or deployable unit. It means that the user interface, server-side logic, and data access layers are part of the same codebase and run as a single process.

> For example, in a monolithic e-commerce application, the product catalog, user authentication, payment system, and order management are all part of one application.


## Structure of a Monolithic Application

A typical monolithic application consists of three main layers:

* **Presentation Layer (UI):** Handles user interactions, such as web pages or mobile UI.
* **Business Logic Layer:** Processes user inputs and makes logical decisions (e.g., validating a purchase).
* **Data Access Layer:** Manages communication with the database.

All these layers are tightly integrated and deployed together.

![image](https://github.com/user-attachments/assets/4c91dda3-316e-4116-86d6-8c454ed91639)


### Key Characteristics

* **Single Codebase:** The entire application is written and maintained in one code repository.
* **Tight Coupling:** Modules are heavily dependent on each other, making separation difficult.
* **Unified Deployment:** The entire application is deployed at once; even small changes require full redeployment.
* **Shared Resources:** All modules share the same memory, storage, and database connection.


### Advantages of Monolithic Architecture

**a. Simple Development**

Developers only need to understand one codebase and one set of technologies. It’s easier for new team members to onboard.

**b. Easy Testing**

Since everything is in one application, integration and end-to-end testing are simpler. Unit tests can be run without mocking external services.

**c. Straightforward Deployment**

There’s only one artifact (e.g., a `.jar`, `.war`, or Docker image) to deploy, making CI/CD pipelines simpler.

**d. Better Performance (Initially)**

There’s no network overhead between services since all components run in the same process. Function calls are faster than inter-service communication.

### Disadvantages of Monolithic Architecture

**a. Scalability Challenges**

If only one part of the application (e.g., payment processing) needs more resources, you still have to scale the entire application, which is resource-inefficient.

**b. Limited Flexibility**

You are usually locked into one technology stack. Refactoring to another language or framework for just one module is hard.

**c. Risky Deployments**

A small bug in one module (like the search feature) can bring down the entire system, since everything is deployed together.

**d. Hard to Maintain**

As the codebase grows, understanding and maintaining it becomes more difficult. Over time, it turns into a **“big ball of mud.”**

**e. Slow Development Speed**

In large teams, developers working on different features may often conflict due to shared dependencies or functions.


### When to Use Monolithic Architecture?

Monolithic architecture is not always bad. It’s **suitable in certain scenarios**, such as:

* **Small or Medium-sized Applications:** Applications with limited business logic and few developers.
* **Startups or MVPs:** Ideal for building a Minimum Viable Product quickly to validate an idea.
* **Tight Deadlines:** Faster to develop and launch compared to microservices.
* **Simple Scaling Needs:** If the app doesn’t need to scale individual features, monolith works well.

### Challenges at Scale

As the application and team grow, the monolith faces several scaling issues:

* **Code Entanglement:** Hard to isolate features for debugging or upgrades.
* **Slow Builds:** Build and deployment times increase significantly.
* **Team Bottlenecks:** Multiple developers working in the same codebase can block each other.
* **Technology Stagnation:** You can't use different technologies for different modules.

This is often when teams consider **splitting the monolith into microservices.**

---

# Microservices Architecture

Microservices Architecture is an architectural style that structures an application as a **collection of small, loosely coupled, independently deployable services**. Each microservice is focused on a specific business function and communicates with others via well-defined APIs (usually HTTP/REST, gRPC, or message queues).

> Example: In an e-commerce application, product catalog, user authentication, order processing, and payment could each be separate services.

![image](https://github.com/user-attachments/assets/5d4c1090-cca0-40d0-9381-601e7eec0c28)


## Key Characteristics

* **Decentralized and Independent:** Each service is developed, deployed, and scaled independently.
* **Single Responsibility:** Each microservice is responsible for one business capability.
* **Technology Diversity:** Different services can use different languages, databases, and frameworks.
* **Inter-Service Communication:** Services interact through APIs or message brokers.
* **Decentralized Data Management:** Each microservice has its own database (no shared DB).
* **Resilience:** Failure in one service doesn’t bring down the entire system.
* **DevOps-Friendly:** Supports CI/CD pipelines, containerization, and orchestration tools (e.g., Docker, Kubernetes).



## Advantages of Microservices

### a. Scalability

You can scale only the services that require more resources (e.g., search or recommendation engine), instead of the whole application.

### b. Independent Deployment

Each team can deploy and update their service without affecting others, reducing downtime and improving agility.

### c. Fault Isolation

A failure in one microservice (e.g., payment) won’t crash the entire application — it may just affect one function.

### d. Technology Flexibility

Teams can choose the best tech stack for their specific use case (e.g., Node.js for API, Python for ML module).

### e. Faster Development

Multiple teams can work in parallel on different services, reducing time to market.

### f. Better Maintainability

Codebase is smaller and focused per service, making it easier to understand, test, and modify.



## Disadvantages of Microservices

### a. Complex Communication

You need to manage inter-service communication, which introduces network latency, timeouts, and failures.

### b. Deployment Overhead

You need robust CI/CD pipelines, monitoring, service discovery, and orchestration tools.

### c. Data Consistency

Each service has its own DB — maintaining consistency (especially for transactions across services) is difficult.

### d. Operational Complexity

Monitoring, logging, debugging, and managing multiple services is harder than in a monolithic app.

### e. Higher Initial Setup Cost

The architecture is overkill for small projects or early MVPs. It needs strong DevOps and infrastructure setup.


## When to Use Microservices

* Large, complex applications with multiple modules
* Applications that require **independent scaling**
* Organizations with **multiple development teams**
* Projects where **continuous deployment** and **technology freedom** are important
* Applications that need **high availability and fault tolerance**


## Design Considerations

* **Database per service:** Ensures loose coupling but requires eventual consistency patterns (e.g., Saga).
* **API Gateway:** Routes client requests to appropriate microservices and handles concerns like authentication, rate limiting.
* **Service Communication:** Use REST for simplicity, gRPC for performance, or message queues for async processing.
* **Observability:** Centralized logging and monitoring are critical.
* **Security:** Each service needs its own authentication/authorization mechanisms or shared token-based validation.


## Real-world Examples

* **Netflix**: Migrated from monolith to hundreds of microservices for scalability and speed.
* **Amazon**: Each team owns and deploys their own microservices independently.
* **Uber**: Broke their monolith into microservices to support rapid global growth and development.

---

# Differences between Monolithic and Microservices Architecture

| Aspect                | **Monolithic Architecture**                                           | **Microservices Architecture**                                |
| --------------------- | --------------------------------------------------------------------- | ------------------------------------------------------------- |
| **Definition**        | Single, unified application where all modules are tightly integrated. | Application broken into small, independent services.          |
| **Codebase**          | One large codebase.                                                   | Multiple smaller codebases per service.                       |
| **Deployment**        | Entire app is deployed at once.                                       | Each microservice is deployed independently.                  |
| **Scalability**       | Scales as a whole unit (resource heavy).                              | Scales individual services as needed (efficient).             |
| **Team Structure**    | One team works on all components.                                     | Different teams manage different services.                    |
| **Technology Stack**  | Usually one tech stack across the app.                                | Each service can use different tech stacks.                   |
| **Communication**     | Internal function calls.                                              | API calls, message queues (inter-service).                    |
| **Failure Impact**    | Failure in one module can crash the whole app.                        | Failures are isolated to the affected service.                |
| **Development Speed** | Fast initially, harder to manage as it grows.                         | Slower to start, but faster for large teams and big projects. |
| **Maintainability**   | Becomes harder as codebase grows.                                     | Easier due to modularity.                                     |
| **Testing**           | End-to-end testing is simpler.                                        | Testing individual services needs more effort.                |
| **Database**          | Shared single database.                                               | Each service has its own database.                            |
| **Best Suited For**   | Small to medium-sized applications or MVPs.                           | Large, complex systems with multiple teams.                   |
