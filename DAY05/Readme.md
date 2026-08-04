# Day 05 – Building Business Logic with Apex (Sprint 4)

## 📖 Overview

On Day 5, I learned why enterprise applications require **business logic** instead of simply storing data. This sprint focused on understanding how software makes business decisions, identifying business rules from customer requirements, and designing a clean application architecture before writing Apex code.

The Placement Management System developed in previous sprints can now store records for students, companies, jobs, and applications. However, it still lacks the intelligence to automatically enforce business rules such as eligibility validation, duplicate prevention, and application deadlines. This sprint introduced the concepts required to solve these real-world business problems.

---

## 🎯 Learning Objectives

* Understand the importance of business logic in enterprise applications.
* Differentiate between data storage and business decision-making.
* Identify business rules from customer requirements.
* Learn how to organize responsibilities using service classes.
* Understand the importance of software architecture before implementation.
* Prepare for Apex development by designing business services.

---

## 🛠 Topics Covered

* Introduction to Business Logic
* Business Requirements vs Business Rules
* Thinking Like a Software Engineer
* Software Architecture
* Single Responsibility Principle (SRP)
* Service Layer Design
* StudentService
* JobService
* ApplicationService
* Preparing for Apex Development

---

## 🏗️ Application Architecture

```text
Student
   │
   ▼
Lightning Web Component (LWC)
   │
   ▼
ApplicationService
   │
   ▼
Eligibility Validation
   │
   ▼
Salesforce Database
   │
   ▼
Confirmation to User
```

This architecture demonstrates the separation of responsibilities:

* **Lightning Web Component (LWC):** Collects user input and displays results.
* **ApplicationService:** Executes business logic and validates business rules.
* **Salesforce Database:** Stores validated records.
* **Confirmation:** Returns the final result to the user.

---

## 📚 Key Concepts

### Business Logic

Business logic is the set of rules that allows software to make decisions based on business requirements instead of simply storing data.

### Business Rules

Examples of business rules include:

* Reject applications submitted after the deadline.
* Prevent duplicate job applications.
* Validate CGPA, branch, and backlog eligibility.
* Notify recruiters after successful applications.
* Prevent duplicate company records.

### Service Layer Design

The application responsibilities are divided into dedicated services:

#### StudentService

Responsible for:

* Registering students
* Updating student profiles
* Verifying academic information
* Checking placement status

#### JobService

Responsible for:

* Creating job postings
* Updating eligibility criteria
* Publishing available jobs
* Closing expired opportunities

#### ApplicationService

Responsible for:

* Receiving student applications
* Checking eligibility
* Preventing duplicate applications
* Saving successful applications
* Returning meaningful messages to users

---

## 💡 Key Takeaways

* Enterprise software should make business decisions automatically.
* Business requirements must be converted into business rules before implementation.
* Every software component should have a single responsibility.
* Good architecture improves maintainability, scalability, and code readability.
* Apex classes represent business services within Salesforce applications.
* Understanding the business problem is the first step toward writing effective Apex code.

---
