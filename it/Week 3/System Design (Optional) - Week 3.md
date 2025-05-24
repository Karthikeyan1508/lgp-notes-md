# High-Level Design (HLD)

High-Level Design is a initial step in development of applications where overall structure of a system is planned. High-Level design focuses mainly on how different components of the system work together without getting to know about internal coding and implementation. This helps everyone involving in the project to understand the goals and ensures good communication during development.

![image](https://github.com/user-attachments/assets/54a49dca-4340-4655-87ee-89f8d1c3aacc)

## Components of HLD

Understanding the components of high-level design is very important for creating effective systems that meets user needs and technical requirements. Below are the main components of high-level design:

1. **System Architecture:** System architecture is an overview of the entire system which represents the structure and the relationships between various components. It helps to visually represent how different parts interact and function.
2. **Modules and Components:** High-Level design breaks down the systems into modules or components each with specific roles and responsibilities, and has a distinct function that contributes to entire system helping in developing an efficient system.
3. **Data Flow Diagrams (DFDs):** Data Flow Diagrams demonstrates the data movement within the system. They help to understand how information is processed and handled.
4. **Interface Design:** This component focuses on how different modules communicate with one another. It details the application programming interfaces (APIs) and user interfaces necessary for seamless interaction between components.
5. **Technology Stack:** The technology stack are various technologies and tools that will be used in the development of the system. This includes programming languages, frameworks, databases.
6. **Deployment Architecture:** It includes how the system will be hosted and accessed. It includes server configurations, cloud infrastructure, and network considerations.

---
## Availability

A system or service's readiness and accessibility to users at any given moment is referred to as availability. It calculates the proportion of time a system is available and functional. Redundancy, fault tolerance, and effective recovery techniques are usually used to achieve high availability, which guarantees that users may use the system without experiencing any major disruptions or downtime.

### How is availability measured?
Availability is measured as the percentage of time a system or service is operational and accessible to users over a specific period. It is expressed using the formula:

```
Availability (%) = ((Uptime) / (Uptime + Downtime)) * 100;
```

### Key Terms:
**Uptime:** The total time a system is operational and functioning as expected.
**Downtime:** The total time the system is unavailable due to failures, maintenance, or other issues.

```
Example:
If a system has 99.9% availability in a year:

Total time in a year: 365 × 24 × 60 = 525,600 minutes
Downtime allowed: 0.1% × 525,600 = 525.6 minutes (~8.76 hours).
```

### Why is Availability Important in System Design?
- User Experience: A positive user experience results from availability, which guarantees that users can access the system and its services when needed. Users become frustrated and may become dissatisfied with systems that are regularly unavailable or encounter downtime.
- Business Continuity: In order to ensure ongoing operations and business continuity, availability is important. Even short outages can cause large financial losses, reputational harm, and legal ramifications for companies that depend on their systems to provide services or carry out transactions.
- Service Level Agreements (SLAs): Many businesses use SLAs to bind themselves to certain availability goals with their stakeholders or consumers. Financial fines or contractual obligations may follow noncompliance with these SLAs.
- Competitive Advantage: Businesses can use high availability as a distinction in the marketplace, especially in sectors where dependability and uptime are crucial. Systems with superior availability over competitors have a higher chance of drawing in and keeping users.
- Disaster Recovery: Resilience and disaster recovery are directly linked to availability. Systems can survive and recover from unforeseen occurrences like hardware failures, network outages, natural disasters, or cyberattacks if they are designed with redundancy, failover mechanisms, and disaster recovery strategies.
- Regulatory Compliance: In many industries, there are regulatory requirements or standards that mandate a minimum level of system availability. Failure to comply with these regulations can result in legal consequences, fines, or sanctions.

### How to achieve high availability?
High availability is necessary for systems that need to run continuously since any disruption could lead to losses in money, reputational damage, or even safety hazards. Systems that usually demand high availability include cloud infrastructure, emergency response services, healthcare systems, e-commerce platforms, and banking apps.

System designers implement various strategies and technologies to achieve high availability, such as:

- Redundancy: Use redundant servers or components so that, in the event of a failure, another can take over without any problems. Data centers, networking, and hardware redundancy are a few examples of this.
- Load balancing: Incoming requests are divided among several servers or resources to enhance system performance and fault tolerance while avoiding overload on any one part.
- Failover mechanisms: Implementing automated processes to detect failures and switch to redundant systems without manual intervention.
- Disaster Recovery (DR): Having a comprehensive plan in place to recover the system in case of a catastrophic event that affects the primary infrastructure.
- Monitoring and Alerting: putting in place reliable monitoring systems that can identify problems instantly and alert administrators so they can act quickly.
- Performance optimization: lowering the possibility of bottlenecks and breakdowns by making sure the system is built and adjusted to efficiently manage the expected load.
- Scalability: Designing the system to scale easily by adding more resources when needed to accommodate increased demand.

## Consistency

Consistency in system design refers to the guarantee that all users or components of a distributed system see the same data at the same time under defined rules. It determines how data is synchronized and made uniform across replicas or services, ensuring that any read operation returns the most recent write or a predictable result depending on the consistency model.

### Why is Consistency Important?
- **Data Integrity:** Consistency ensures that every user or system component has access to correct and up-to-date information, which is vital for making accurate decisions and processing transactions.
- **User Trust:** When users get consistent responses from the system regardless of where or when they access it, it builds trust in the application.
- **Preventing Conflicts:** In multi-user or distributed environments, consistent data prevents issues like double-bookings, incorrect balances, or conflicting updates.

### Types of Consistency Models:
- **Strong Consistency:** Guarantees that any read will return the most recent write. This is essential for systems like banking where precision is non-negotiable.
- **Eventual Consistency:** Ensures that if no new updates are made, all replicas will eventually reflect the same value. Systems like DNS and social media feeds use this model to improve performance and availability.
- **Causal Consistency:** Maintains the order of causally-related operations across nodes, useful in collaborative tools like shared documents.
- **Read-Your-Writes Consistency:** Ensures that a user sees their own updates immediately, even if global consistency is not guaranteed.

### Consistency in the CAP Theorem
According to the CAP theorem, a distributed system can achieve only two out of the following three guarantees: Consistency, Availability, and Partition Tolerance. Many systems opt for availability and partition tolerance at the cost of strong consistency, instead using eventual consistency models to balance trade-offs.

### Techniques to Achieve Consistency
- **Quorum-Based Reads/Writes:** Requires a minimum number of nodes to agree on the read/write operation before proceeding.
- **Replication Protocols:** Ensures consistency across copies of data using master-slave or multi-leader architectures.
- **Conflict Resolution:** Implements version control, vector clocks, or custom reconciliation logic to resolve data conflicts when nodes sync.

---

## Reliability

Reliability in system design is the ability of a system to operate correctly and consistently over time, even in the face of failures. A reliable system is one that continues to function without errors or unexpected behavior, ensuring the delivery of services to users as intended.

### Why is Reliability Important?
- **User Satisfaction:** Systems that frequently crash or return incorrect results frustrate users and erode trust.
- **Business Continuity:** Reliable systems minimize the risk of service interruptions, helping organizations maintain productivity and operations.
- **Financial Impact:** Unreliable systems can lead to significant revenue losses, especially in industries like finance, e-commerce, or healthcare.
- **Regulatory Compliance:** Many sectors require a minimum standard of reliability. Failing to meet these can result in penalties or legal repercussions.
- **Operational Efficiency:** High reliability reduces the burden on technical support and operations teams by minimizing incidents and service desk tickets.

### Key Concepts:
- **Fault Tolerance:** The ability to continue operations when parts of the system fail. Achieved by duplicating critical components (hardware or services).
- **Redundancy:** Deploying multiple instances of a component so the system can fall back on one if another fails.
- **Failover Mechanisms:** Automatically transferring operations from a failed system component to a backup.
- **Replication and Backups:** Regularly copying data and system states to ensure recovery from corruption or deletion.
- **Graceful Degradation:** Designing systems to continue offering limited functionality during failures rather than shutting down entirely.
- **Monitoring and Alerting:** Continuously observing system health and sending alerts in case of anomalies for quick remediation.
- **Disaster Recovery:** Preparing for large-scale failures with a comprehensive plan that includes recovery time objectives (RTO) and recovery point objectives (RPO).

### Metrics to Measure Reliability:
- **Mean Time to Failure (MTTF):** Average time between failures.
- **Mean Time to Recovery (MTTR):** Average time taken to recover after a failure.
- **Error Rate:** Number of errors per transaction or operation.
- **Uptime:** Total time the system is running without disruption.

### How to Achieve High Reliability?
Designing a reliable system requires architectural decisions that prevent single points of failure, allow for seamless failover, and ensure system components degrade gracefully. Strategies include:
- Using **replicated databases** across zones or regions.
- Employing **microservices** so that a failure in one module doesn’t affect the entire system.
- Implementing **automated testing** to catch bugs early.
- Regular **incident response drills** to ensure teams can handle real failures effectively.

---
