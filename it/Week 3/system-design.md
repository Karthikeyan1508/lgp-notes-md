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
