# Placement Management System – Day 03

## Overview

This project is a Salesforce-based Placement Management System developed to automate the student placement process using Salesforce declarative tools. The goal of Day 03 was to design the core data model and implement business automation using Record-Triggered Flows, Formula Fields, and Validation Rules.

---

## Objectives

- Design the data model for the Placement Management System.
- Create custom objects and relationships.
- Automate application processing using Flow Builder.
- Enforce business rules using Validation Rules.
- Learn how Formula Fields can be used to reference related records.

---

# Objects Created

## Student

Stores student information.

### Fields

| Field | Type |
|--------|------|
| Student Name | Text |
| Roll Number | Text (Unique) |
| Email | Email |
| Phone | Phone |
| CGPA | Number |
| Department | Picklist |
| Graduation Year | Number |

---

## Job

Stores job details published by companies.

### Fields

| Field | Type |
|--------|------|
| Job Title | Text |
| Company Name | Text |
| Minimum CGPA | Number |
| Package (LPA) | Currency |
| Job Closing Date | Date |
| Location | Text |
| Job Description | Long Text Area |

---

## Application

Represents a student's application for a job.

### Fields

| Field | Type |
|--------|------|
| Application Number | Auto Number |
| Student | Lookup(Student) |
| Job | Lookup(Job) |
| Application Date | Date |
| Status | Picklist |
| Remarks | Long Text Area |
| Student CGPA | Formula |
| Required CGPA | Formula |

---

# Object Relationships

```
Student
    │
    │ Lookup
    ▼
Application
    ▲
    │ Lookup
    │
Job
```

Each Application record belongs to one Student and one Job.

---

# Record-Triggered Flow

## Flow Name

Auto Populate Application Date

## Flow Type

Before-Save Record-Triggered Flow

## Business Requirement

Whenever a new Application record is created, automatically populate the Application Date with the current date.

## Implementation

- Object: Application
- Trigger: Record Created
- Flow Type: Fast Field Updates (Before Save)
- Action:
    - Application Date = Current Date

---

# Formula Fields

## Student CGPA

Formula

```text
Student__r.CGPA__c
```

Displays the CGPA of the selected Student.

---

## Required CGPA

Formula

```text
Job__r.Minimum_CGPA__c
```

Displays the minimum CGPA required for the selected Job.

---

# Validation Rule

## Rule Name

Validate_Student_CGPA

## Business Requirement

A student should not be allowed to apply if their CGPA is lower than the minimum CGPA required for the selected job.

## Formula

```text
Student_CGPA__c < Required_CGPA__c
```

## Error Message

```
Student CGPA is below the minimum CGPA required for this job.
```

---

# Testing

### Test Case 1

Student CGPA: 9.10

Minimum CGPA: 6.50

Expected Result:

✅ Application saved successfully.

---

### Test Case 2

Student CGPA: 7.20

Minimum CGPA: 7.50

Expected Result:

❌ Validation Rule prevents the Application from being saved.

---

# Salesforce Features Used

- Custom Objects
- Custom Fields
- Lookup Relationships
- Formula Fields
- Validation Rules
- Record-Triggered Flow
- Flow Builder

---

# Learning Outcomes

After completing Day 03, I learned how to:

- Design a Salesforce data model.
- Create custom objects and relationships.
- Build Before-Save Record-Triggered Flows.
- Use Formula Fields to retrieve values from related records.
- Enforce business rules using Validation Rules.
- Test and verify Salesforce automation.

---

# Screenshots

The following screenshots are included in the repository.

- Student Object
- Job Object
- Application Object
- Record-Triggered Flow
- Formula Fields
- Validation Rule
- Successful Application Creation
- Validation Rule Error

---

# Future Enhancements

- Prevent duplicate applications.
- Email notification to Placement Officer.
- Automatic Offer Letter generation.
- Reports and Dashboards.
- Apex Triggers.
- Lightning Web Components (LWC).

---

## Author

**Joseph Roland**

Salesforce Developer Trainee
