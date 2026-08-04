# 🚀 Day 06 - Building Business Transactions with SOQL, DML and Apex

## 📖 Overview

Day 6 focused on one of the most fundamental aspects of Salesforce development—**working with data**. During this sprint, I learned how Salesforce applications retrieve, validate, and manipulate records using **SOQL (Salesforce Object Query Language)**, **DML (Data Manipulation Language)**, and **Apex**.

The session began by introducing SOQL and DML concepts, explaining how enterprise applications first retrieve business information before making decisions. After understanding these concepts, I implemented CRUD (Create, Read, Update, Delete) operations using Apex.

The second part of the sprint simulated a real-world Placement Management System where multiple SOQL queries, business validations, and DML operations were combined to build a complete business transaction. This demonstrated how professional Salesforce developers design maintainable, scalable, and business-oriented applications.

---

# 🎯 Learning Objectives

By the end of this sprint, I was able to:

- Understand why business applications depend on accurate information.
- Learn the role of SOQL in Salesforce.
- Retrieve records efficiently using SOQL.
- Understand DML operations and when to use them.
- Create, update, and delete Salesforce records.
- Build complete business transactions using Apex.
- Apply business validation before modifying data.
- Write clean and maintainable Salesforce code.
- Understand enterprise-level engineering principles.

---

# 🏢 Business Scenario

This sprint was based on a **Placement Management System**.

When a student clicks the **Apply** button for a company, the application cannot immediately process the request.

Instead, it must:

1. Retrieve student information.
2. Retrieve job eligibility criteria.
3. Check whether the student has already applied.
4. Validate eligibility rules.
5. Create an application record.
6. Save the record.
7. Return a confirmation message.

This reflects how enterprise Salesforce applications process business transactions.

---

# 🛠️ Technologies Used

- Salesforce Developer Edition
- Apex Programming Language
- SOQL (Salesforce Object Query Language)
- DML (Data Manipulation Language)
- Salesforce Developer Console
- Execute Anonymous Window
- Debug Logs

---

# 📚 Concepts Covered

## Salesforce Objects

Salesforce stores business information inside **Objects**.

Example:

| Object | Purpose |
|---------|----------|
| Student__c | Student Information |
| Job__c | Job Details |
| Application__c | Student Applications |

---

## SOQL (Salesforce Object Query Language)

SOQL is used to retrieve information from Salesforce Objects.

General Syntax

```sql
SELECT Fields
FROM ObjectName
WHERE Condition
```

Example

```apex
SELECT Name, CGPA__c
FROM Student__c
WHERE Name='Joseph'
LIMIT 1
```

### Key Features Learned

- SELECT
- FROM
- WHERE
- LIMIT
- Retrieving only required fields
- Query optimization

---

## DML (Data Manipulation Language)

DML is used to manipulate Salesforce records.

Operations learned:

- Insert
- Update
- Delete

---

# 💻 Practical Exercises

## Exercise 1 – Create a Student Record

### Objective

Create a new Student record.

### Apex Code

```apex
Student__c student = new Student__c(
    Name='Joseph',
    CGPA__c=8.7
);

insert student;
```

### Result

Successfully inserted a new Student record into Salesforce.

---

## Exercise 2 – Retrieve Student Information

### Objective

Retrieve the student record using SOQL.

### Apex Code

```apex
Student__c student = [
    SELECT Name,CGPA__c
    FROM Student__c
    WHERE Name='Joseph'
    LIMIT 1
];

System.debug(student);
```

### Result

Successfully retrieved the Student record and displayed it in Debug Logs.

---

## Exercise 3 – Update Student Record

### Objective

Update the student's CGPA.

### Apex Code

```apex
Student__c student=[
SELECT Id,CGPA__c
FROM Student__c
WHERE Name='Joseph'
LIMIT 1
];

student.CGPA__c=9.1;

update student;
```

### Result

Successfully updated the student's CGPA.

---

## Exercise 4 – Delete Student Record

### Objective

Delete the Student record.

### Apex Code

```apex
Student__c student=[
SELECT Id
FROM Student__c
WHERE Name='Joseph'
LIMIT 1
];

delete student;
```

### Result

Successfully removed the Student record.

---

# 🏗️ Engineering Sprint

After learning SOQL and DML, the sprint shifted toward building a **complete enterprise business transaction**.

Instead of writing isolated CRUD operations, multiple business services were combined into one workflow.

---

## Sprint Backlog

| Story ID | User Story | Priority |
|----------|------------|----------|
| US-7 | Retrieve Student Information | High |
| US-8 | Retrieve Job Eligibility | High |
| US-9 | Prevent Duplicate Applications | High |
| US-10 | Create Application Record | High |
| US-11 | Update Application Status | Medium |
| US-12 | Return User Feedback | Medium |

---

# 🔄 Business Transaction Flow

```text
Receive Application Request
            │
            ▼
Retrieve Student Details
            │
            ▼
Retrieve Job Eligibility
            │
            ▼
Check Duplicate Applications
            │
            ▼
Validate Eligibility
            │
            ▼
Create Application Record
            │
            ▼
Save Record using DML
            │
            ▼
Return Confirmation
```

This workflow represents how a real Salesforce application processes business requests.

---

# ⚙️ Engineering Principles Learned

Throughout the sprint, I learned several software engineering principles:

- Retrieve only the information required.
- Avoid unnecessary SOQL queries.
- Retrieve only required fields.
- Perform business validation before DML.
- Keep methods focused on a single responsibility.
- Write readable and maintainable Apex code.
- Separate retrieval, validation, and update logic.

---

# 🧠 Design Considerations

The sprint emphasized writing maintainable software by avoiding common mistakes such as:

- Repeating the same SOQL query in multiple methods.
- Retrieving unnecessary fields.
- Executing DML before validation.
- Writing very large methods with multiple responsibilities.

Instead, responsibilities should be divided into smaller reusable methods.

---

# 🔍 SOQL vs DML

| SOQL | DML |
|------|------|
| Retrieves records | Modifies records |
| Uses SELECT | Uses Insert, Update, Delete |
| Read-only | Changes data |
| Returns records | Saves records |

---


# 🎤 Interview Preparation

### What is SOQL?

SOQL (Salesforce Object Query Language) is used to retrieve records from Salesforce objects.

---

### What is DML?

DML (Data Manipulation Language) is used to create, update, and delete Salesforce records.

---

### Why should SOQL be executed before DML?

Because business applications must retrieve the required information before validating rules and modifying data.

---

### Why should DML be executed after validation?

Executing DML before validation may insert or update incorrect business data.

---

### Why should only required fields be retrieved?

Retrieving unnecessary fields consumes additional resources and affects application performance.

---

# 💡 Key Takeaways

- Business applications depend on accurate information.
- SOQL retrieves business data.
- DML modifies business data.
- Business validation should always occur before DML.
- Every SOQL query should answer one business question.
- Enterprise applications combine multiple SOQL queries and DML operations into complete business transactions.
- Clean architecture improves readability, maintainability, and scalability.

---


# 🎯 Conclusion

Day 6 introduced the complete lifecycle of handling data in Salesforce applications. I learned how to retrieve records using SOQL, manipulate records using DML, and integrate these operations into a complete business transaction using Apex.

Beyond CRUD operations, this sprint emphasized software engineering principles such as data-driven decision making, validation before database updates, efficient querying, and modular application design. These concepts provide a strong foundation for advanced Salesforce topics such as Triggers, Batch Apex, Lightning Web Components, and enterprise application development.

---
