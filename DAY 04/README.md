# 📅 Day 04 - Your First Lightning Web Component (LWC)

## 📖 Overview

On Day 4, I learned the fundamentals of Lightning Web Components (LWC), Salesforce's modern UI framework. I built my first Placement Portal interface using HTML, JavaScript, and Salesforce Lightning Design System (SLDS). The project focused on understanding component structure, data binding, event handling, and dynamic UI updates without using Apex.

---

# 🎯 Objectives

- Understand Lightning Web Components (LWC)
- Learn the structure of an LWC
- Build a user interface
- Display dynamic data using JavaScript
- Handle button click events
- Understand data binding
- Deploy an LWC to a Lightning App Page

---

# 🚀 Project Built

I built a simple **Placement Portal Dashboard** that includes:

- Student Information
- Current Date
- Placement Statistics
- Welcome Message Button
- Apply Button
- Dynamic Status Update

---

# 🛠 Technologies Used

- Salesforce Developer Edition
- Lightning Web Components (LWC)
- HTML
- JavaScript
- SLDS (Salesforce Lightning Design System)

---

# 📂 Component Structure

```
placementHome
│── placementHome.html
│── placementHome.js
└── placementHome.js-meta.xml
```

---

# ✨ Features Implemented

### Student Details

- Student Name
- Roll Number
- Department

### Placement Dashboard

- Number of Companies
- Number of Jobs
- Applications Submitted

### Dynamic Date

Displays today's date using JavaScript.

### Show Welcome Message

Displays a welcome message when the button is clicked.

### Apply Button

Changes application status from:

```
Not Applied
```

to

```
Applied
```

using JavaScript.

---

# 📚 README Questions

## 1. What is LWC?

Lightning Web Components (LWC) is Salesforce's modern UI framework built on standard web technologies such as HTML, JavaScript, and CSS. It is used to build fast, reusable, and maintainable user interfaces for Salesforce applications.

---

## 2. What did you build?

I built a Placement Portal dashboard that displays student information, placement statistics, today's date, and interactive buttons for displaying a welcome message and updating application status.

---

## 3. Which file contains HTML?

`placementHome.html`

This file contains the user interface including text, buttons, and layout.

---

## 4. Which file contains JavaScript?

`placementHome.js`

This file contains variables, business logic, event handling, and dynamic functionality.

---

## 5. What did you learn today?

Today I learned:

- Lightning Web Components
- LWC Folder Structure
- HTML Templates
- JavaScript in LWC
- Data Binding
- Event Handling
- Conditional Rendering
- Deploying Components to Lightning App Builder

---

# 💼 Interview Questions

## 1. What is Lightning Web Components?

Lightning Web Components (LWC) is Salesforce's modern UI framework based on web standards that helps developers build fast, reusable, and maintainable user interfaces.

---

## 2. Why did Salesforce introduce LWC?

Salesforce introduced LWC to improve application performance, simplify development using modern JavaScript standards, and replace the older Aura framework.

---

## 3. Difference between LWC and Aura

| LWC | Aura |
|------|------|
| Built on Web Standards | Salesforce Proprietary Framework |
| Better Performance | Slower than LWC |
| Easier to Learn | More Complex |
| Uses Modern JavaScript | Uses Aura Syntax |

---

## 4. What are the three files inside an LWC?

- HTML File
- JavaScript File
- Meta XML File

---

## 5. Why is JavaScript required?

JavaScript is used to store variables, perform logic, handle events, and update the user interface dynamically.

---

## 6. What is Data Binding?

Data binding is the process of displaying JavaScript variables inside the HTML template using `{ }`. Whenever the variable changes, the UI updates automatically.

---

## 7. Can LWC directly execute SOQL?

No. LWC cannot execute SOQL directly. It communicates with Apex classes, which execute SOQL queries.

---

## 8. Why does LWC need Apex?

LWC uses Apex to perform server-side operations such as querying Salesforce data, performing DML operations, and implementing business logic.

---

## 9. Where is the component deployed?

The component is deployed to a Lightning App Page using Lightning App Builder.

---

## 10. Explain the component you built today.

I created a Placement Portal dashboard using Lightning Web Components. It displays student details, placement statistics, today's date, and includes interactive buttons for displaying a welcome message and updating the application status.

---

# 📸 Screenshots

(Add screenshots here)

- Placement Portal
- Student Details
- Welcome Message
- Apply Button
- Status Updated

---

# 🎓 Learning Outcome

By completing this project, I gained hands-on experience with Lightning Web Components, component deployment, data binding, JavaScript event handling, and building interactive Salesforce user interfaces.

---

# 👨‍💻 Author

**Joseph Roland**

B.Tech Computer Science Engineering

Learning Salesforce Development 🚀
