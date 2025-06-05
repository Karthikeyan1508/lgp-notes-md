# Introduction to Data Integrity

**Data Integrity** is a fundamental concept in database systems that ensures the **accuracy**, **consistency**, and **reliability** of data throughout its entire lifecycle — from entry and storage to retrieval and modification.

It ensures that the data stored in a database remains correct, complete, and trustworthy, regardless of user actions, system failures, or malicious attempts to alter the data. It protects data from being corrupted either by accidental human errors, hardware/software faults, or unauthorized access.

---

## Why is Data Integrity Important?

- **Accuracy**: Prevents invalid or incorrect data entries (e.g., letters in an age field).
- **Consistency**: Keeps relationships and dependencies across tables logically valid.
- **Reliability**: Ensures that stored data truly represents the real-world entity it models.
- **Security**: Reduces the chance of unauthorized modifications or inconsistent updates.
- **Compliance**: Helps organizations meet legal and regulatory standards (e.g., GDPR, HIPAA).
- **Business Decisions**: Enables organizations to make better decisions based on clean and accurate data.
- **Audit and Traceability**: Ensures changes are accountable and traceable.

---

## How is Data Integrity Maintained?

Data integrity is enforced using:

- **Integrity constraints** (e.g., primary key, foreign key, check).
- **Database triggers** and **assertions** for complex validation rules.
- **Transactions and ACID properties** (Atomicity, Consistency, Isolation, Durability).
- **Access control and user privileges** to restrict unauthorized changes.
- **Data validation rules** in both frontend and backend layers.

---

## Example

In a **hospital management system**, incorrect patient data (e.g., wrong blood group or missing emergency contact) can be life-threatening. Data integrity ensures that only valid and verified information is stored and maintained across all departments.

---

## Types of Integrity Constraints

### A. Entity Integrity

- **Definition**:  
  Ensures each row in a table is uniquely identified using a **Primary Key** that cannot be NULL.

- **Example**:  
  In a college, each student has a unique roll number. No two students can have the same roll number, and every student must have one.

---

### B. Referential Integrity

- **Definition**:  
  Ensures that a **foreign key** value in one table always refers to an existing **primary key** in another table.

- **Example**:  
  In a university hostel system, each student is assigned a Block Number from the Blocks table. If a student is linked to a block number that doesn’t exist, that’s a violation.

---

### C. Domain Integrity

- **Definition**:  
  Ensures that the data entered in a column is within the defined **data type**, **format**, or **range**.

- **Example**:  
  In an online shopping site, the age field should only accept valid numbers between 18 and 65.

---

### D. User-defined Integrity

- **Definition**:  
  Rules created by users based on specific business needs, not covered by the above constraints. Implemented using **assertions** or **triggers**.

- **Example**:  
  In a bank, the total loan amount issued from a branch should never exceed the total deposits at the branch.

---

## Implementing Constraints

### Primary Key

- **Used to**: Uniquely identify each row. Cannot be null or duplicate.
- **Example**:  
  In an exam result database, each student must have a unique roll number.

---

### Foreign Key

- **Used to**: Create a link between two tables.
- **Example**:  
  Each order in an e-commerce site must be linked to a valid customer.

---

### CHECK Constraint

- **Used to**: Limit values in a column.
- **Example**:  
  A flight booking system allows only “Economy”, “Business”, or “First Class” seat types.

---

## Cascading Updates and Deletes

### ON DELETE CASCADE

- **Description**:  
  If a row in the parent table is deleted, all related rows in the child table are also deleted.

- **Example**:  
  In a school system, if a student is removed, all their exam results should be deleted automatically.

---

### ON UPDATE CASCADE

- **Description**:  
  If the primary key in the parent table is updated, the corresponding foreign key in the child table is also updated.

- **Example**:  
  In a library, if a book ID is updated in the Books table, the new ID should reflect in the Issued_Books table as well.

---

## Final Summary Table with Example

| Constraint Type         | Purpose                                        | Example                                                        |
|-------------------------|------------------------------------------------|----------------------------------------------------------------|
| Entity Integrity        | Ensure each row is unique and not NULL         | Unique Roll Numbers in college                                 |
| Referential Integrity   | Ensure valid references across tables          | Orders linked to valid Customers                               |
| Domain Integrity        | Valid values in each column                    | Age between 18–65; Name should be text                         |
| User-defined Integrity  | Custom business rules                          | Loans should not exceed total deposits at a bank               |
| Primary Key             | Unique, not NULL identifier                    | Student_ID, Aadhaar Number                                     |
| Foreign Key             | Reference to another table's primary key       | Student assigned to a valid hostel block                       |
| CHECK Constraint        | Restrict column values                         | Only allow 'Gold', 'Silver', 'Platinum' as membership types    |
| ON DELETE/UPDATE CASCADE| Maintain referential consistency automatically | Deleting customer also deletes their orders automatically       |

---
# **Comprehensive Guide to Database Security**

## **1. Database Security: A Detailed Overview**
Database security refers to the collective measures used to protect databases from unauthorized access, data breaches, and corruption. The **Database Administrator (DBA)** is responsible for implementing these security controls.

### **1.1 Key Security Measures with Examples**

#### **1.1.1 Authentication**
- **Definition:** Verifies the identity of users before granting access.
- **Methods:**
  - **Username & Password:** Basic but widely used (e.g., logging into a banking system).
  - **Multi-Factor Authentication (MFA):** Combines passwords with OTPs or biometrics (e.g., Google Authenticator for database logins).
  - **Biometrics:** Fingerprint or retina scans (e.g., Apple’s Face ID for secure database access).

**Example:**  
A hospital database requires doctors to authenticate using both a password and a fingerprint scan to access patient records.

#### **1.1.2 Access Control**
- **Definition:** Restricts users to only the data they are permitted to access.
- **Types:**
  - **Discretionary Access Control (DAC):** Owners decide who can access data.
  - **Mandatory Access Control (MAC):** System-enforced access rules (e.g., military databases).
  - **Role-Based Access Control (RBAC):** Permissions based on job roles (e.g., HR can view salaries, but not IT).

**Example:**  
In a university database:
- **Students** can view their grades.
- **Professors** can update grades.
- **Admins** can modify course registrations.

#### **1.1.3 Inference Control**
- **Definition:** Prevents users from deducing sensitive information from non-sensitive data.
- **Example:**  
  - A database allows querying average salaries but blocks queries that could reveal an individual’s salary (e.g., "What is the salary of the only female manager in department X?").

#### **1.1.4 Flow Control**
- **Definition:** Ensures data does not leak to unauthorized users.
- **Example:**  
  - A bank’s internal database prevents customer transaction details from being accidentally sent to an external marketing team.

#### **1.1.5 Statistical Database Security**
- **Definition:** Allows aggregate queries but blocks individual record access.
- **Example:**  
  - A government database permits queries like "How many people in California earn over $100k?" but not "What is John Doe’s salary?"

#### **1.1.6 Encryption**
- **Definition:** Converts data into unreadable format unless decrypted with a key.
- **Example:**  
  - **Credit card numbers** in an e-commerce database are stored as encrypted hashes (e.g., `A1B2-C3D4-E5F6` → `X9Y8-Z7W6-V5U4`).

---

## **2. Database Access Control: User Roles and Privileges (Deep Dive)**
### **2.1 Types of Privileges**
| **Privilege** | **Description** | **Example** |
|--------------|----------------|------------|
| **SELECT** | Read data | Viewing customer records |
| **INSERT** | Add new data | Adding a new employee |
| **UPDATE** | Modify data | Changing a product price |
| **DELETE** | Remove data | Deleting an inactive user |
| **GRANT** | Assign privileges | Allowing a manager to grant access |

### **2.2 Implementing Role-Based Access Control (RBAC)**
- **Step 1:** Define roles (Admin, Manager, Employee, Guest).
- **Step 2:** Assign privileges to roles.
- **Step 3:** Assign users to roles.

**Example in SQL:**
```sql
-- Create roles
CREATE ROLE Admin;
CREATE ROLE Employee;

-- Grant privileges
GRANT SELECT, INSERT, UPDATE ON Employees TO Admin;
GRANT SELECT ON Employees TO Employee;

-- Assign users to roles
GRANT Admin TO user_john;
GRANT Employee TO user_sarah;
```

### **2.3 Best Practices**
- **Least Privilege Principle:** Give users only necessary access.
- **Regular Audits:** Check who accessed what data.
- **Session Timeouts:** Automatically log out inactive users.

---

## **3. Preventing SQL Injection & XSS (With Real-World Examples)**
### **3.1 SQL Injection (SQLi)**
#### **3.1.1 How It Works**
- Attackers inject malicious SQL into input fields.
- **Example Attack:**  
  ```sql
  -- Normal login query:
  SELECT * FROM Users WHERE username = 'admin' AND password = '1234';

  -- Malicious input (password field):
  ' OR '1'='1
  -- Resulting query (bypasses login):
  SELECT * FROM Users WHERE username = 'admin' AND password = '' OR '1'='1';
  ```

#### **3.1.2 Prevention Techniques**
1. **Parameterized Queries (Prepared Statements)**
   ```python
   # Safe (Python + SQLite example)
   cursor.execute("SELECT * FROM Users WHERE username = ? AND password = ?", (user, pwd))
   ```
2. **Input Validation**
   - Reject inputs like `' OR 1=1 --`.
3. **Stored Procedures**
   ```sql
   CREATE PROCEDURE LoginUser(IN user VARCHAR, IN pwd VARCHAR)
   AS BEGIN
     SELECT * FROM Users WHERE username = user AND password = pwd;
   END;
   ```

### **3.2 Cross-Site Scripting (XSS)**
#### **3.2.1 How It Works**
- Attackers inject malicious scripts into web pages.
- **Example Attack:**  
  ```html
  <!-- Malicious comment in a blog -->
  <script>alert('XSS Attack!');</script>
  ```
  - If stored in a database, this script executes for all users.

#### **3.2.2 Prevention Techniques**
1. **Input Sanitization**
   - Remove `<script>` tags before storing data.
2. **Content Security Policy (CSP)**
   - HTTP header to block inline scripts:
     ```
     Content-Security-Policy: default-src 'self'
     ```
3. **HTTP-Only Cookies**
   - Prevent JavaScript from accessing session cookies.

---

## **4. Backup & Recovery: Ensuring Data Durability**
### **4.1 Backup Strategies**
| **Type** | **Description** | **Example Use Case** |
|---------|----------------|----------------------|
| **Full Backup** | Complete copy of data | Weekly server backup |
| **Incremental Backup** | Only changes since last backup | Daily log backups |
| **Differential Backup** | Changes since last full backup | Mid-week updates |
| **Mirror Backup** | Exact real-time copy | Financial databases |

### **4.2 Recovery Techniques**
1. **Point-in-Time Recovery (PITR)**
   - Restore database to a specific time.
   - **Example:**  
     ```sql
     -- PostgreSQL PITR
     RESTORE DATABASE Sales TO TIMESTAMP '2024-05-20 14:00:00';
     ```
2. **Disaster Recovery Plan**
   - **Steps:**
     1. Identify critical systems.
     2. Store backups offsite (AWS S3, Azure Blob).
     3. Test recovery procedures.

### **4.3 Real-World Example: Ransomware Attack**
- **Scenario:** A company’s database is encrypted by ransomware.
- **Solution:**  
  - Restore from last clean backup.
  - Use **immutable backups** (cannot be altered by attackers).

---

## **5. Data Encryption at Rest & in Transit**
### **5.1 Encryption at Rest**
- **Methods:**
  - **Transparent Data Encryption (TDE):** Encrypts entire database files.
    ```sql
    -- SQL Server TDE
    CREATE DATABASE ENCRYPTION KEY WITH ALGORITHM = AES_256;
    ```
  - **Column-Level Encryption:** Encrypts sensitive fields (e.g., SSNs).
    ```sql
    -- MySQL example
    INSERT INTO Patients (name, ssn) VALUES ('John', AES_ENCRYPT('123-45-6789', 'key'));
    ```

### **5.2 Encryption in Transit**
- **Methods:**
  - **TLS/SSL:** Secures web traffic (e.g., HTTPS for database APIs).
  - **VPN:** Encrypts remote connections (e.g., employees accessing a corporate DB).

### **5.3 Key Management**
- **Best Practices:**
  - Use **Hardware Security Modules (HSMs)** for key storage.
  - Rotate keys periodically (e.g., every 90 days).

---

## **Conclusion**
- **Database Security:** Requires authentication, access control, and encryption.
- **Access Control:** Implement RBAC and least privilege.
- **SQLi/XSS Prevention:** Use parameterized queries and input sanitization.
- **Backup & Recovery:** Follow the 3-2-1 rule (3 copies, 2 media types, 1 offsite).
- **Encryption:** Encrypt data both at rest and in transit.

By applying these measures, organizations can protect sensitive data from breaches and ensure compliance with regulations like **GDPR** and **HIPAA**.
