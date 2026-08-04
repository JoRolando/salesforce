# 🚀 Day 06 - Retrieving and Managing Information with SOQL and DML

## 📖 Overview

Day 6 focused on one of the core concepts of Salesforce development—**working with data**. Until now, the Apex programs developed in previous sessions primarily executed business logic. In this session, I learned how to interact with Salesforce records using **SOQL (Salesforce Object Query Language)** and **DML (Data Manipulation Language)**.

Every Salesforce application relies on data stored in objects. Before making any business decision, an application must retrieve the required information from the database. Once the necessary information is available, the application can process it, validate business rules, and update the records when required.

During this practical session, I performed complete **CRUD (Create, Read, Update, Delete)** operations on a custom Salesforce object using Apex in the Developer Console.

---

# 🎯 Learning Objectives

By the end of this session, I was able to:

- Understand why enterprise applications depend on accurate data retrieval.
- Learn how Salesforce stores data inside objects.
- Understand the role of SOQL in retrieving Salesforce records.
- Understand the purpose of DML operations.
- Retrieve records using SOQL.
- Insert new records using Apex.
- Update existing Salesforce records.
- Delete records from Salesforce.
- Read and interpret Debug Logs.
- Perform complete CRUD operations using Apex.

---

# 🏢 Business Scenario

Consider a Placement Management System.

When a student clicks the **Apply** button for a company, the application cannot immediately decide whether the student is eligible.

Instead, it must first retrieve information such as:

- Student Name
- CGPA
- Department
- Active Backlogs
- Graduation Year
- Existing Applications
- Job Eligibility Criteria
- Application Deadline

Only after retrieving this information can Salesforce determine whether the student is eligible to apply.

This illustrates one of the most important principles learned during this session:

> **Retrieve information first. Make business decisions afterwards.**

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

## 1. Salesforce Objects

Salesforce stores information inside **Objects**, similar to tables in a relational database.

Example:

**Student__c**

| Field | Description |
|--------|-------------|
| Name | Student Name |
| CGPA__c | Student CGPA |

---

## 2. SOQL (Salesforce Object Query Language)

SOQL is used to retrieve records from Salesforce objects.

It is similar to SQL but is specifically designed for Salesforce.

General syntax:

```sql
SELECT field_names
FROM ObjectName
WHERE condition
```

Example:

```apex
SELECT Name, CGPA__c
FROM Student__c
WHERE Name = 'Joseph'
LIMIT 1
```

This query retrieves the Name and CGPA of the student named **Joseph**.

---

## 3. DML (Data Manipulation Language)

DML is used to modify data stored in Salesforce.

The DML operations covered during this session include:

- Insert
- Update
- Delete

---

# 💻 Practical Implementation

---

## Exercise 1 – Creating a Student Record (INSERT)

### Objective

Create a new Student record using Apex and save it inside Salesforce.

### Apex Code

```apex
Student__c student = new Student__c(
    Name = 'Joseph',
    CGPA__c = 8.7
);

insert student;
```

### Explanation

- Created a new Student object.
- Assigned values to Name and CGPA.
- Used the **insert** DML statement to save the record into Salesforce.

### Expected Output

A new Student record is successfully created.

---

## Exercise 2 – Retrieving Records using SOQL

### Objective

Retrieve the Student record created in the previous exercise.

### Apex Code

```apex
Student__c student = [
    SELECT Name, CGPA__c
    FROM Student__c
    WHERE Name = 'Joseph'
    LIMIT 1
];

System.debug(student);
```

### Explanation

- Queried the Student object.
- Retrieved only the required fields.
- Stored the returned record inside an Apex variable.
- Displayed the retrieved record using Debug Logs.

### Output

```
Student__c
Name = Joseph
CGPA = 8.7
```

---

## Exercise 3 – Updating an Existing Record

### Objective

Modify the CGPA of an existing Student record.

### Apex Code

```apex
Student__c student = [
    SELECT Id, CGPA__c
    FROM Student__c
    WHERE Name = 'Joseph'
    LIMIT 1
];

student.CGPA__c = 9.1;

update student;
```

### Explanation

- Retrieved the Student record.
- Updated the CGPA value.
- Saved the modified record using the **update** DML statement.

### Output

The Student's CGPA was successfully updated from **8.7** to **9.1**.

---

## Exercise 4 – Deleting a Record

### Objective

Delete the Student record.

### Apex Code

```apex
Student__c student = [
    SELECT Id
    FROM Student__c
    WHERE Name = 'Joseph'
    LIMIT 1
];

delete student;
```

### Explanation

- Retrieved the Student record.
- Used its unique Id.
- Deleted the record using the **delete** DML statement.

### Output

The Student record was successfully removed from Salesforce.

---

# 🔍 SOQL vs DML

| SOQL | DML |
|------|------|
| Retrieves data | Modifies data |
| Uses SELECT | Uses Insert, Update, Delete |
| Does not modify records | Changes database records |
| Returns records | Saves changes permanently |

---
# 💡 Key Takeaways

- Every business application depends on accurate data.
- SOQL is used to retrieve Salesforce records.
- DML is used to manipulate Salesforce data.
- Every update and delete operation requires the record's unique Id.
- CRUD operations form the foundation of Salesforce application development.
- Debug Logs are essential for verifying Apex execution and troubleshooting issues.

---


# 🎯 Conclusion

Day 6 introduced the essential techniques for interacting with Salesforce data. By combining SOQL and DML with Apex, I learned how to build applications capable of retrieving information, applying business logic, and updating records efficiently.

These concepts serve as the foundation for more advanced Salesforce development topics such as Triggers, Controllers, Batch Apex, and Lightning Web Components, where data retrieval and manipulation are performed extensively.

---

## ⭐ Repository Purpose

This repository documents my Day 6 learning as part of my Salesforce Developer journey. It demonstrates the implementation of SOQL queries and DML operations using Apex through hands-on CRUD exercises and serves as a reference for future Salesforce projects and interview preparation.
