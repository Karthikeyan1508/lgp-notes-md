<!-- Informal Design Guidelines for Relational Databases  -->
# Informal Design Guidelines for Relational Databases
# 1. What is Relational Database Design?

Relational database design is the process of grouping attributes to form "good" relation schemas. The main aim is to design schemas that store data efficiently, eliminate redundancy,and avoid update anomalies. 

There are two levels of relation schemas:

●​ Logical (User View) Level: Describes how data is understood and used by the end-users.

●​ Storage (Base Relation) Level: Describes how data is actually stored in the database. 

# 2. Informal Guidelines for Good Relational Design

Before applying formal rules like normal forms, the following informal design guidelines should be followed: 

## GUIDELINE 1: Semantics of Relation Attributes 

Each tuple in a relation should represent one real-world entity or relationship instance.

●​ Attributes from different entities (e.g., EMPLOYEEs, DEPARTMENTs, PROJECTs) should not be mixed in the same relation. 

●​ Only foreign keys should be used to refer to other entities.

●​ Keep entity attributes and relationship attributes as separate as possible.

Bottom Line: Design schemas that are easy to explain and understand. Each attribute's meaning (semantics) should be clear. 

## GUIDELINE 2: Avoid Redundancy and Update Anomalies

Mixing attributes from different entities often results in redundant information and update anomalies, such as: 

 Insertion Anomalies: Can't insert data unless unrelated data is also provided.

●​ Deletion Anomalies: Deleting data may cause loss of valuable information.

 Modification Anomalies: Updating data in one place requires changes in many rows.

Example: EMP_PROJ (Emp#, Proj#, Ename, Pname, No_hours)

●​ If the name of project P1 changes from "Billing" to "Customer-Accounting", it must be updated in all rows where employees work on P1. 

●​ You can’t insert a project unless an employee is assigned to it.

●​ Deleting an employee may result in the deletion of the project if that employee is the only one assigned. 

Guideline 2 Conclusion: Design schemas that avoid redundancy and these anomalies. If anomalies are unavoidable, document them for application-level handling. 

## GUIDELINE 3: Minimize Null Values in Tuples

Schemas should be designed such that NULL values are minimized.

●​ Attributes frequently having NULL values should be placed in separate relations.

●​ Reasons for NULL values:

○​ Attribute not applicable or invalid 

○​ Attribute value unknown 

○​ Attribute exists but unavailable at the time 

Guideline 3 Conclusion: Avoid designs that force unnecessary NULLs, as they complicate querying and logic. 

GUIDELINE 4: Avoid Spurious Tuples (Ensure Lossless Joins)

Bad schema designs can produce spurious (meaningless) tuples during JOIN operations.

●​ The design must satisfy the lossless join property: When relations are joined, no incorrect or extra tuples should be created. 

●​ This is verified through the non-additive (lossless) join property.

Two Important Properties of Decomposition:

●​ (a) Lossless join (non-additive join) – must be satisfied.

●​ (b) Dependency preservation – desirable but can be compromised if needed. 

Guideline 4 Conclusion: Always ensure decompositions are lossless to maintain data integrity. 

# Functional Dependencies (FDs)

Functional Dependencies (FDs) are critical in relational database design. They define the relationship between attributes and help assess the quality of a schema. 

# Definition of Functional Dependency

A functional dependency, denoted as $\mathbf {X}\rightarrow \mathbf {Y}$ , exists in a relation $R$  if: 

●​ For any two tuples $t1$  and t2 in any valid instance of R,

$\text {Ift1}[\mathrm {X}]=\mathbf {t}2[\mathrm {X}]$  then $\mathbf {t}\mathbf {1}[\mathbf {Y}]=\mathbf {t}\mathbf {2}[\mathbf {Y}]$ 

This means the values of attributes in $X$  uniquely determine the values of attributes in Y.

# Purpose and Role of FDs 

●​ FDs capture real-world constraints between data attributes.

●​ They are used to define keys.

●​ They help detect redundancy and determine if a schema should be normalized. 

# Examples of Functional Dependencies

1.​ $SSN\rightarrow ENAME$ 

○​ A social security number uniquely determines the employee name.

2.​ PNUMBER $\rightarrow$ , PLOCATION}

$。$  Project number determines both project name and its location. 

3.​ {SSN, PNUMBER} $\rightarrow$ HOURS

○​ A combination of employee SSN and project number determines how many hours the employee works on that project. 

## Why FDs Are Important:

Functional dependencies are used to:

●​ Define primary keys, candidate keys, and super keys.

●​ Identify anomalies (update, insert, delete).

●​ Drive normalization into 1NF, 2NF, 3NF, and BCNF.

●​ Validate schema quality based on rules and constraints.

# Types of Functional Dependencies

## 1. Trivial Functional Dependency

●​ Occurs when the dependent attributes are a subset of the determinant.

●​ Always true and not useful for schema optimization.

Example: {EmpID, Name} $\rightarrow$ EmpID 

This is trivial because EmpID is already part of the left-hand side.

# 2. Non-Trivial Functional Dependency 

●​ Occurs when the dependent attributes are not a subset of the determinant.

●​ These are meaningful for schema design.

Examples: EmpID $\rightarrow$ DeptName 

EmpID does not contain DeptName, hence it’s non-trivial.

# 3. Full Functional Dependency

●​ A functional dependency $\mathrm {X}\rightarrow \mathrm {Y}$ is full if no subset of X can determine Y.

## ●​ Relevant in identifying violations of 2NF.

Examples: $\{\text {EmpID,ProjID}\}\rightarrow \text {Hou}$ rs

This is full if:

-​ ProjID alone does not determine Hours 

-​EmpID alone does not determine Hours

# 4. Partial Dependency 

●​ Occurs when a subset of a composite key determines a non-prime attribute.

●​ Causes violation of 2NF.

​Examples: StudentID $\rightarrow$ StudentName(In a table where the primary key is {StudentID, CourseID}:) 

-​This is a partial dependency (StudentName depends on part of the key).

# 5. Transitive Dependency 

●​ If $\mathrm {A}\rightarrow \mathrm {\sim B}$  and $\mathrm {B}\rightarrow \mathrm {C}$ , then $\mathrm {A}\rightarrow \mathrm {C}$  is a transitive dependency.

●​ It causes violation of 3NF when a non-key attribute is transitively dependent on a key.​

Examples:

EmpID $\rightarrow$ DeptID 

DeptID $\rightarrow$ DeptManager 

$\Rightarrow \text {EmpID}\rightarrow \mathrm {D}$ eptManager (Transitive)

# 6. Multivalued Dependency (MVD) (used in 4NF)

●​ Denoted as X →→ Y

●​ Indicates that for each value of X, there is a set of Y values independent of other attributes 

Example:

EmpName →→ Skill 

EmpName →→ Dependent

This means:

-​Employee can have multiple dependents

-​Skills and dependents are independent

-​Employee can have multiple skills.

# Introduction to Normalization

●​ Normalization is the process of decomposing unsatisfactory or poorly designed relations by breaking up their attributes into smaller, well-structured relations. 

●​ A normal form is a set of criteria (based on keys and functional dependencies) that a relation must satisfy to be considered "well-formed." 

# 1. Types of Normal Forms

a)​ 1NF (First Normal Form)

b)​ 2NF (Second Normal Form)

c)​ 3NF (Third Normal Form)

d)​ BCNF (Boyce-Codd Normal Form) 

e)​ 4NF (Fourth Normal Form)

f)​ 5NF (Fifth Normal Form) 

Higher normal forms often require checking additional properties like lossless join and dependency preservation. 

# 2. Key Properties of a Good Decomposition

●​ Lossless Join Property: Guarantees no spurious (incorrect) tuples are generated when decomposed tables are joined. 

●​ Dependency Preservation Property: Ensures all functional dependencies from the original relation are preserved in the decomposed set of relations. 

# 3. Practical Use of Normal Forms 

●​ Normalization is widely used in practice to ensure data integrity, reduce redundancy, and avoid anomalies. 

●​ Designers typically normalize up to 3NF or BCNF, rarely going beyond unless necessary. 

##  Note: 

●​ In some scenarios, full normalization may reduce performance due to complex joins. 

●​ Denormalization is the reverse process where tables in higher normal forms are merged (joined) into a single relation to improve query performance. 

# 4. Key Concepts: Definitions of Keys

Superkey 

●​ A set of attributes S in relation R is a superkey if no two tuples in any legal relation state r(R) will have the same values for S. 

Candidate Key

●​ A candidate key is a minimal superkey. That means removing any attribute from it would make it no longer unique. 
●​ There can be multiple candidate keys in a relation.

Primary Key and Secondary Keys

●​ One candidate key is designated as the primary key.
●​ Others are called secondary keys.

Prime and Nonprime Attributes

●​ A prime attribute is an attribute that is part of any candidate key.
●​ A nonprime attribute is not part of any candidate key.

# Anomalies in DBMS

## What is Anomaly?

An anomaly means an inconsistency or deviation from the normal pattern. In Database Management Systems (DBMS), an anomaly refers to inconsistency that occurs in a relational table during operations such as insertion, deletion, or update. 

These anomalies usually occur due to poor database design, such as:

●​ Storing too much redundant data

●​ Storing all information in a single table without normalization

Such issues compromise the integrity of the database. To resolve these anomalies, normalization is applied, where large tables are split into smaller related tables using various types of joins. 

## Types of Anomalies in DBMS

### 1. Update Anomaly 

Occurs when updating data in multiple rows leads to inconsistency.

Example: 


| Worker_<br>id  | Worker_<br>name  | Worker_<br>dept  | Worker_address  |
| --- | --- | --- | --- |
| 65  | Ramesh  | ECT001  | Jaipur  |
| 65  | Ramesh  | ECT002  | Jaipur  |
| 73  | Amit  | ECT002  | Delhi  |
| 76  | Vikas  | ECT501  | Pune  |
| 76  | Vikas  | ECT502  | Pune  |
| 79  | Rajesh  | ECT669  | Mumbai  |


In the table above, if Ramesh's address changes, we must update all rows with Ramesh. If we miss one, it results in inconsistency. 

### 2. Insertion Anomaly 

Occurs when we cannot insert data due to missing information in a non-null column.

Example:​

 If we want to add a new worker who is not assigned to any department, we cannot insert the row because the department column cannot be null. 

### 3. Deletion Anomaly

Occurs when deleting a row also removes unintended data.

#### Example:​

 If we delete the department ECT669, all data related to Rajesh is also deleted, leading to loss of important information. 

#### Solution: Normalization

To remove anomalies, we normalize the tables. Normalization involves dividing large tables into smaller, well-structured ones. Some common normal forms are: 

●​ First Normal Form (1NF)

●​ Second Normal Form (2NF) 

●​ Third Normal Form (3NF)

●​ Boyce-Codd Normal Form (BCNF)​

#### Example 2: Student Table 

| Stu_<br>id  | Stu_<br>name  | Stu_<br>branch  | Stu_club  |
| --- | --- | --- | --- |
| 2018nk01 | Shivani |  Computer | Literature | Science 
| 2018nk01 | Shivani | Computer | Dancing | Science |
| 2018nk02 | Ayush |  Electronics  | Videography |
| 2018nk03 | Mansi | Electrical | Dancing |
| 2018nk03 | Mansi |  Electrical |  Singing|
| 2018nk04 | Gopal | Mechanical | Photography |

#### Update Anomaly

If Shivani changes her branch from Computer Science to Electronics, all her rows must be updated. If we miss one, it will result in inconsistency. 

#### Insertion Anomaly

If we want to insert a new student Ankit who is not part of any club, we cannot insert the record since the stu_club column cannot be null. 

#### Deletion Anomaly

If we delete the Photography club, Gopal's entire record will also be deleted, even though we only intended to remove the club. 

## Types of Normal Forms

### a)​ First Normal Form (1NF)

The domain of each attribute contains only atomic (indivisible) values.The value of each attribute in a tuple must be a single value from the domain.​

## Characteristics of 1NF

**-No** **composite** **attributes** (attributes that can be broken into smaller subparts)

- **No** **multivalued** **attributes** (attributes with multiple values in a single tuple)

**- No nested relations**

**- Every attribute must hold only atomic values**

**Normalization into 1NF**

**Figure** **14.8** Normalization into 1NF. (a) Relation schema that is not in 1NF. (b) Example relation instance. (c) 1NF relation with redundancy.

(a) DEPARTMENT

<!-- DNAME DNUMBER DMGRSSN DLOCATIONS -->
![](https://web-api.textin.com/ocr_image/external/356f2f5f23bf776c.jpg)

(b) DEPARTMENT


| DNAME  | DNUMBER  | DMGRSSN  | DLOCATIONS  |
| --- | --- | --- | --- |
| Research  | 5  | 333445555  | {Bellaire, Sugarland, Houston} |
| Administration  | 4  | 987654321  | {Stafford} |
| Headquarters  | 1  | 888665555  | {Houston} |


(c) DEPARTMENT


| DNAME  | DNUMBER  | DMGRSSN  | DLOCATION  |
| --- | --- | --- | --- |
| Research  | 5  | 333445555  | Bellaire  |
| Research  | 5  | 333445555  | Sugarland  |
| Research  | 5  | 333445555  | Houston  |
| Administration  | 4  | 987654321  | Stafford  |
| Headquarters  | 1  | 888665555  | Houston  |


<!-- Addison Wesley Longman, Inc. 2000, Elmasri/Navathe, Fundamentals of Database Systems, Third Edition -->

## b) Second Normal Form (2NF)

## Concepts Used in 2NF

●​ Based on functional dependencies (FDs) and primary key.

●​ Focuses on eliminating partial dependencies.

## Key Definitions:

●​ Prime Attribute: An attribute that is part of a candidate key.

●​ Full Functional Dependency: A functional dependency X → Y is full if removing any attribute from X causes the dependency to no longer hold.​

## Examples: 

●​ {SSN, PNUMBER} → HOURS is a full FD, since neither SSN → HOURS nor PNUMBER → HOURS holds individually. 

●​ {SSN, PNUMBER} → ENAME is not a full FD. It is a partial dependency because SSN → ENAME also holds. 

## Definition 

## A relation schema R is in Second Normal Form (2NF) if: 

●​ It is in 1NF. 

●​ Every non-prime attribute is fully functionally dependent on the entire primary key. 

## Purpose of 2NF

●​ Eliminates partial dependencies that cause redundancy and anomalies.

## 2NF Normalization Process 

●​ Identify all partial dependencies.

●​ Decompose the relation into two or more relations such that each relation contains only full dependencies. 

Applying 2NF helps reduce redundancy related to partial key dependencies and improves data integrity. 

### c) Third Normal Form (3NF)

## Transitive Functional Dependency 

●​ A functional dependency $\mathbf {X}\rightarrow \mathbf {Z}$  is transitive if it can be derived from $\mathbf {X}\rightarrow \mathbf {Y}$ and $\mathbf {Y}\rightarrow \mathbf {Z}.$  

### ●​ Example:

$。$  $SSN\rightarrow DNUMBER$ 

$。$ ​ DNUMBER $\rightarrow$ DMGRSSN 

$。$  Therefore, $SSN\rightarrow$ DMGRSSN is transitive.

### ●​ Non-transitive example: 

○​ $SSN\rightarrow$ ENAME is non-transitive because there is no attribute $X$  such that: 

 ​ $\text {SSN}\rightarrow \mathrm {X}$  and $X\rightarrow$ ENAME​

## Definition

## A relation schema R is in Third Normal Form (3NF) if:

1.​ It is in Second Normal Form (2NF), and

2.​ No non-prime attribute is transitively dependent on the primary key.

## Important Note 

●​ In a transitive dependency $\mathrm {X}\rightarrow \mathrm {Y}\rightarrow \mathrm {Z},$  where X is the primary key:

○​ It's only a problem if Y is not a candidate key.

$。$ ​ If Y is a candidate key, it's not considered a violation of 3NF.

### Example:

## EMP(SSN, Emp#, Salary)

·SSN→Emp#→Salary

· If Emp# is a candidate key, then this transitive dependency is not a 3NF violation.

**Normalizing into 2NF and 3NF**

<!-- EMP_PROJ Ssn Pnumber Hours Ename Pname Plocation FD1 FD2 FD3 2NF Normallzation EP1 EP2 EP3 Ssn Pnumber Hours Ssn Ename Pnumber Pname Plocation FD1 FD2 FD3 -->
![](https://web-api.textin.com/ocr_image/external/377e18a8be6c928e.jpg)

**(b)**

<!-- EMP_DEPT Ename Ssn Bdate Address Dnumber Dname Dmgr_ssn 3NF Normallzation ED1 ED2 Ename Bdate Address Dnumber Dnumber Dname -->
![](https://web-api.textin.com/ocr_image/external/65d36b502d1f5e43.jpg)

Dmgr_ssn

**Figure 15.11**

Normalzing Into 2NF and 3NF. (a) Normalizing EMP_PROJ Into 2NF relations. (b) Normalzing EMP_DEPT Into 3NF relations.

<!-- **Normalization into 2NF and 3NF** -->

### Figure 15.12

Normaltzation Into 2NF and 3NF.(a) The LOTS relation with its functional dependencles FD1 through FD4. (b) Decomposing Into the 2NF relations LOTS1 and LOTS2.(c)Decomposing LOTS1 Into the 3NF relations LOTS1A and LOTS1B. (d) Summary of the progressive normaltzation of LOTS.

**(m)**

<!-- Candidato Koy Proporty County. name Lote Area Price Tax rate FD1 FD2 FD3 FD4 -->
![](https://web-api.textin.com/ocr_image/external/8138ca18d6fc975e.jpg)

(b)

LOTS2


| County name  | County name  | Jate  |
| --- | --- | --- |
| FDa  |  |  |


<!-- LOTS1 Property County name LotA Area Prices FD1 FD2 FD4 -->
![](https://web-api.textin.com/ocr_image/external/ecf04b87299d3cb2.jpg)

**(c)**

LOTS1B


| Area  | Price  |
| --- | --- |
| FD4  |  |


<!-- LOTS1A Property ice County_name Lote Area FD1 FD2 -->
![](https://web-api.textin.com/ocr_image/external/25c27cc92035d479.jpg)

**(d)**

INF

<!-- LOTS LOTS1 LO LOTS1A LOT S2 -->
![](https://web-api.textin.com/ocr_image/external/7aa72796f8e50003.jpg)

2NF

3NF

## d) Boyce-Codd Normal Form (BCNF)

## Definition:

## A relation schema R is in BCNF if:

·For every functional dependency X→A in R,

· X is a superkey of R.

## Hierarchy of Normal Forms:

·Each higher normal form is stricter than the previous:

o 1NF C 2NF C 3NF C BCNF

○ Every:

2NF relation is also in 1NF

3NF relation is also in 2NF

BCNF relation is also in 3NF

## Important Notes:

·There exist relations that are in 3NF but not in BCNF.

· The ideal goal is to decompose all relations into BCNF (or at least 3NF) to avoid redundancy and anomalies.

**Boyce-Codd normal form**

Figure 14.12 Boyce-Codd normal form. (a) BCNF normalization with the dependency of FD2 being “lost" in the decomposition.

(b) A relation R in 3NF but not in BCNF.

(a) LOTS1A

<!-- PROPERTY_ID# COUNTY_NAME LOT# AREA FD1 FD2 FD5 BCNF Normalization LOTS1AX LOTS1AY -->
![](https://web-api.textin.com/ocr_image/external/291abb1dfe1f849a.jpg)


| AREA  | COUNTY_NAME |
| --- | --- |



| PROPERTY_ID# | AREA  | LOT# |
| --- | --- | --- |


(b)

<!-- R A B C FD1 FD2 -->
![](https://web-api.textin.com/ocr_image/external/a0fcf6b04c09a705.jpg)

<!-- Addison Wesley Longman, Inc. 2000, Elmasri/Navathe, Fundamentals of Database Systems, Third Edition -->

## A relation TEACH that is in 3NF but not in BCNF

**Figure** **14.13** A relation TEACH that is in 3NF but not in BCNF.

TEACH


| STUDENT  | COURSE  | INSTRUCTOR  |
| --- | --- | --- |



| Narayan  | Database  | Mark  |
| --- | --- | --- |
| Smith  | Database  | Navathe  |
| Smith  | Operating Systems  | Ammar  |
| Smith  | Theory  | Schulman  |
| Wallace  | Database  | Mark  |
| Wallace  | Operating Systems  | Ahamad  |
| Wong  | Database  | Omiecinski  |
| Zelaya  | Database  | Navathe  |


Addison Weslay Longman, Inc. 2000, Elmasri/Navathe, Fundamentals of Database Systems, Third Edition

## Achieving BCNF by Decomposition

**Example:** Relation TEACH

Given functional dependencies:

· FD1: {student, course} →instructor

· FD2: instructor→course

## Analysis:

· {student, course} is a candidate key.

· But since instructor → course holds, and instructor is not a superkey, this violates BCNF.

· Hence, the relation is in 3NF but not in BCNF.

## Need for Decomposition

●​ A relation not in BCNF must be decomposed to satisfy BCNF.

●​ However, during decomposition: 

$。$  Preservation of all functional dependencies might be lost.

○​ But non-additivity (lossless join) must not be sacrificed.

## Possible Decompositions of TEACH: 

1.​ {student, instructor} and {student, course}

2.​ {course, instructor} and {course, student}

3.​ {instructor, course} and {instructor, student}

## Comparison of Decompositions: 

●​ All three decompositions lose FD1: {student, course} $\rightarrow$  instructor 

●​ Only the 3rd decomposition satisfies the non-additivity (lossless join) property — it avoids generating spurious tuples. 

## e) Multivalued Dependencies (MVDs) and Fourth Normal Form (4NF)

Multivalued Dependency (MVD) — Definition A multivalued dependency $X\rightarrow >Y$  on relation R means: If two tuples t1 and t2 exist with the same X values, then the following must also be true: 

●​ There must be two other tuples t3 and t4 such that:

$。$  $\mathrm {t}3[\mathrm {X}]=\mathrm {t}4[\mathrm {X}]=\mathrm {t}1[\mathrm {X}]=\mathrm {t}2[\mathrm {X}]$ 

○​ $\mathrm {t}3[\mathrm {Y}]=\mathrm {t}1[\mathrm {Y}],\mathrm {t}4[\mathrm {Y}]=\mathrm {t}2[\mathrm {Y}]$ 

○​ $\mathrm {t}3[Z]=\mathrm {t}2[Z],\mathrm {t}4[Z]=\mathrm {t}1[Z],$  where $Z=\mathrm {R}-(\mathrm {X}\cup \mathrm {Y})$ 

Trivial MVD:

●​ $\mathrm {Y}\subseteq \mathrm {X},$  or

● $X\cup Y=R$ 

EMP Example: Relation EMP(ENAME, PNAME, DNAME) has two MVDs:

●​ ENAME —&gt;&gt; PNAME

●​ $\text {ENAME}longrightarrow\text {DNAME}$ 

### This requires decomposition into:

·EMP_PROJECTS(ENAME, PNAME)

· EMP_DEPENDENTS(ENAME, DNAME) These decompositions are in 4NF.

(a) **EMP**


| ENAME  | PNAME  | DNAME  |
| --- | --- | --- |
| Smith  | X  | John  |
| Smith  | Y  | Anna  |
| Smith  | X  | Anna  |
| Smith  | Y  | John  |


(d)

## (b) EMP_PROJECTS


| ENAME  | PNAME  |
| --- | --- |
| Smith  | X  |
| Smith  | Y  |


**EMP_DEPENDENTS**


| E NAME  | DNAME  |
| --- | --- |
|Smith | John |
| Smith | Anna |

**Fourth Normal Form (4NF)-Definition** A relation R is in 4NF if**:**

·For every nontrivial MVD X-&gt;&gt; Y, X is a superkey of R.

(c) **SUPPLY**


| SNAME  | PARTNAME  | PROJNAME  |
| --- | --- | --- |
| Smith  | Bolt  | Projx  |
| Smith  | Nut  | ProjY  |
| Adamsky  | Bolt  | ProjY  |
| Walton  | Nut  | Projz  |
| Adamsky  | Nail  | Projx  |
| Adamsky  | Bolt  | Projx  |
| Smmith  | Bolt  | ProjY  |


**R1**


| SNAME  | PARTNAME  |
| --- | --- |
| Smith  | Bolt  |
| Smith  | Nut  |
| Adamsky  | Bolt  |
| Walton  | Nut  |
| Adamsky  | Nail  |


**R2**


| SNAME  | PROJNAME  |
| --- | --- |
| Smith  | Projx  |
| Smith  | ProjY  |
| Adamsky  | ProjY  |
| Walton  | Projz  |
| Adamsky  | Projx  |


**R3**


| PARTNAME  | PROJNAME  |
| --- | --- |
| Bolt  | Projx  |
| Nut  | ProjY  |
| Bolt  | ProjY  |
| Nut  | Projz  |
| Nail  | Projx  |


Note: Functional dependencies are also considered a type of MVD, so 4NF handles both.

### Inference Rules for MVDs (MVD counterparts to FD rules)

1.​ IR1 (Reflexivity for FDs): $\text {If}\mathrm {X}\supseteq \mathrm {Y}\text {,}$ $\text {then}\mathrm {X}\rightarrow \mathrm {Y}$ 

2.​ IR2 (Augmentation for FDs): $\mathrm {X}\rightarrow \mathrm {Y}$  implies $XZ\rightarrow YZ$ 

3.​ IR3 (Transitivity for FDs): $\mathrm {X}\rightarrow \mathrm {Y}$ , $Y\rightarrow Z$  implies $X\rightarrow Z$ 

4.​ IR4 (Complementation for MVDs): $X\rightarrow Y$  implies $Xlongrightarrow(\mathrm {R}-(\mathrm {X}\cup \mathrm {Y}))$ 

5.​ IR5 (Augmentation for MVDs): $X\rightarrow Y$  implies $\mathrm {WX}longrightarrow\mathrm {YZif}\mathrm {\sim W}\subseteq \mathrm {Z}$ 

6.​ IR6 (Transitivity for MVDs): $X\rightarrow Y$ , $Y\rightarrow Z$  implies $\mathrm {X}longrightarrow(\mathrm {Z}-\mathrm {Y})$ 

7.​ IR7 (FD to $MVD):X\rightarrow Y$ implies $X\rightarrow Y$ 

8.​ IR8 (Coalescence): $\text {If}X\rightarrow >\mathrm {Y}$ $andW\rightarrow Z,$  and W ∩ $\mathrm {Y}=\varnothing ,$  and $\mathrm {Y}\subseteq \mathrm {Z},\text {then}\mathrm {X}\rightarrow \mathrm {Z}$ 

### 4NF Decomposition Lossless Join (Non-additive) condition (LJ1’): Decomposition of R into R1 and R2 is lossless if: 

$·(R1\cap R2)\rightarrow >(R1-R2),$  or

$·(R1\cap R2)\rightarrow >(R2-R1)$ This ensures no spurious tuples are generated.

### Algorithm 11.5 – Decomposition into 4NF Input: Universal relation R and a set $F$  of FDs and MVDs Steps: 

1.​ Initialize $\mathrm {D}:=\{\mathrm {R}\}$ 

2.​ While there exists a relation $\mathrm {Q}\in \mathrm {D}$  not in 4NF:

○​ Find a nontrivial MVD $X\rightarrow Y$  that violates 4NF 

○​ Replace Q with:

 ​ $(\mathrm {Q}-\mathrm {Y})$ 

$(\mathrm {X}\cup \mathrm {Y})$

### Join Dependency (JD)

Imagine you have a big table of data.

A Join Dependency says:

"You should be able to break this table into smaller pieces (sub-tables), and then join them back together to get the original table — without any extra or missing rows." 

### Example:

Suppose you break a table into 3 parts:

R1, R2, and R3

Join(R1, R2, R3) = Original Table

Then there's a join dependency.

●​ It's called non-additive or lossless because nothing is lost or added.

●​ If you just break it and can’t get the same table back, then it’s not a proper JD.

Special Case: When you split the table into just 2 parts, it's a Multivalued Dependency (MVD) — a simpler version of JD. 

### f) Fifth Normal Form (5NF)

5NF is the highest level of normalization in databases.

 It says:

"A table is in 5NF if it can’t be broken into smaller tables using a join dependency unless those smaller parts are based on a key." 

Why is this important?

To remove all hidden or complex redundancy from the table.

This happens mostly in very complex databases with lots of interrelated data.

### Relation SUPPLY with Join Dependency and conversion to Fifth Normal Form

#### Figure 11.4

Fourth and fifth normal forms.

(a) The EMP relation with two MVDs:Ename $\rightarrow >$ Pname and Ename $\rightarrow$ Dname.

(b) Decomposing the EMP relation into two 4NF relations EMP_PROJECTS and EMP_DEPENDENTS.

(c) The relation SUPPLY with no MVDs is in 4NF but not in 5NF if it has the JI $\mathrm {D}\left(R_{1},R_{2},R_{3}\right)$ 

(d) Decomposing the relation SUPPLY into the 5NF relations $R_{1},R_{2},R_{3}$ 

**(c)** **SUPPLY**

(d)


| S  name  | Part_name  | Proj_name  |
| --- | --- | --- |
| Smith  | Bolt  | ProjX  |
| Smith  | Nut  | ProjY  |
| Adamsky  | Bolt  | ProjY  |
| Walton  | Nut  | ProjZ  |
| Adamsky  | Nail  | Projx  |
| Adamsky  | Bolt  | Projx  |
| Smith  | Bolt  | ProjY  |


$$R_{1}$$


| Sname  | Part name  |
| --- | --- |
| Smith  | Bolt  |
| Smith  | Nut  |
| Adamsky  | Bolt  |
| Walton  | Nut  |
| Adamsky  | Nail  |


$$R_{3}$$


| Part name  | Proj name  |
| --- | --- |
| Bolt  | Projx  |
| Nut  | ProjY  |
| Bolt  | ProjY  |
| Nut  | ProjZ  |
| Nail  | Projx  |


$$R_{2}$$


| Sname  | Proj name  |
| --- | --- |
| Smith  | Projx  |
| Smith  | ProjY  |
| Adamsky  | ProjY  |
| Walton  | ProjZ  |
| Adamsky  | Projx  |



| Normal<br>Form  | Rule/ Condition  | Example Before  | Example After  |
| --- | --- | --- | --- |
| 1NF (First Normal<br>Form)  | All attributes must have atomic (indivisible) values  | Student(ID, Name, Courses)<br>CN}<br>Courses $=$ {DBMS, | Student(ID, Name, Course)<br>1 row per course  |
| 2NF<br>(Second  | In 1NF and no partial dependency<br>(non-prime attribute  | Enrollment(SID,<br>CID,SName)  | Decompose into:<br>Student(SID,SName)  |
| Normal <br>Form)  | depends only on part of the key)  | → SName depends only on SID, not (SID, CID)  | Enrollment(SID, CID)  |
| 3NF (Third Normal <br>Form)  | In 2NF and no transitive dependency (non-prime attribute depends on another non-key attribute)  | Employee(EID, <br>DNo, DName) <br>→ EID → DNo → DName  | Decompose into: <br>Employee(EID, DNo) <br>Department(DNo, DName)  |
| BCNF <br>(Boyce-Co dd Normal Form)  | For every FD X → Y, <br>X must be a superkey  | Teach(Student, <br>Course, Instructor) FDs: {Student, Course} → Instructor <br>Instructor → Course (violates BCNF)  | Decompose into: <br>Instructor(Instructor, <br>Course) <br>Teach(Student, Instructor)  |
| 4NF <br>(Fourth <br>Normal <br>Form)  | In BCNF and no multivalued <br>dependency (MVD) unless LHS is superkey  | Emp(EName, Skill, Project) <br>Emp has many Skills and Projects independently  | Decompose into: <br>EmpSkill(EName, Skill) <br>EmpProject(EName, <br>Project)  |
| 5NF (Fifth Normal <br>Form)  | In 4NF and no join dependency unless implied by candidate keys  | Supply(Supplier, <br>Part, Project) <br>→ Complex join dependencies  | Decompose into: <br>SupplierPart(Supplier, <br>Part) <br>SupplierProject(Supplier, Project) <br>PartProject(Part, Project)  |


## Denormalization

### What is Denormalization?

When we normalize tables, we break them into multiple smaller tables. While this improves data integrity and reduces redundancy, retrieving data from multiple tables often requires performing joins, which can be time-consuming. Denormalization is a technique that eliminates the drawbacks of normalization by adding redundant data to the database, thus reducing the need for joins and improving query performance. 

Note:

Denormalization does not mean avoiding normalization. It is an optimization strategy used after normalization to improve performance. 

## Example of Denormalization

Consider two tables, students and branches, after performing normalization. 

### Normalized Tables: 

#### ●​Students Table:


| roll_no  | stud_name  | age  | branch_id  |
| --- | --- | --- | --- |
| 1  | Alice  | 20  | 101  |
| 2  | Bob  | 22  | 102  |


#### ●​Branch Table: 

|branch_id |  branch_name | 
| --- | --- |
| 101 | Computer Science |

102  Mechanical

To retrieve both the student name and the branch name, a JOIN operation is needed between these two tables. 

Issue: 

If these tables are large, joining them can take a long time, especially when frequent updates or queries are required. 

Solution:

We can denormalize the database by adding the branch_name directly to the students table, thus eliminating the need for a join.​

### Denormalized Students Table:


| $roll_no$  | stud_name  | age  | branch_id  | branch_name  |
| --- | --- | --- | --- | --- |
| 1  | Alice  | 20  | 101  | Computer Science  |
| 2  | Bob  | 22  | 102  | Mechanical  |


Now, we don’t need to perform joins to retrieve data, which speeds up queries.

### Pros of Denormalization

#### 1.​ Enhance Query Performance:

 Fetching queries in a normalized database often requires joining several tables. With denormalization, redundancy is added to the database, reducing the number of joins required, which improves query performance.​

#### 2.​ Convenient Database Management:

 Denormalization makes it easier to manage databases as fewer tables need to be processed. It also reduces the time spent calculating values on-the-fly during queries.​

#### 3.​ Facilitates and Accelerates Reporting:

 For frequently required reports, like annual revenue tracking, denormalization simplifies the process by storing redundant data, thus speeding up report generation. Without denormalization, queries would need to search the entire database, slowing down the process.​

### Cons of Denormalization

#### 1.​ Increased Storage Requirements:

 Denormalization adds redundant data, which increases storage usage.

#### 2.​ More Expensive Updates and Inserts:​

 Updating or inserting data can be more expensive, as changes must be made in multiple places (due to redundancy).​

#### 3.​ More Complex Update and Insert Operations:​

 Denormalization makes writing code for updates and inserts more complicated since the same data might need to be updated in several places.​

#### 4.​ Risk of Data Inconsistency:​

 With redundant data, there is a risk of inconsistency. Every instance of a piece of data must be updated to maintain integrity.​

Normalization vs Denormalization 


| Dimension  | Normalization  | Denormalization  |
| --- | --- | --- |
| Primary Goal  | Reduce redundancy, enforce integrity  | Improve read performance, reduce JOIN overhead  |
| Structure  | Many narrow, relational tables  | Fewer wide, flat tables with redundancy  |
| Data Integrity  | Strong — single source of truth  | Weaker — data duplication can <br>introduce inconsistencies  |
| Write <br>Performance  | Efficient — less to update  | Slower — same data may need to be <br>updated in many places  |
| Read <br>Performance  | Slower — requires joins  | Faster — pre-joined or duplicated fields  |
| Query Complexity  | Higher — JOINs and <br>normalization-aware query logic  | Lower — simpler, more direct queries  |
| Storage Usage  | Lower — no duplicated values  | Higher — redundant data across rows  |
| ETL/ELT <br>Complexity  | Simple — clear rules, clean <br>transformations  | Complex — requires sync logic for <br>duplicated fields  |
| Schema Evolution  | Easier — each table models one <br>concept  | Harder — changes may cascade across multiple fields  |
| Best Suited For  | OLTP, operational systems with <br>strong consistency needs  | OLAP, analytics, dashboards, and <br>real-time reporting  |

