# Software Design Document

## Table of Contents

1. [Introduction](#1-introduction)
   1. [Objective](#11-objective)
   2. [Scope](#12-scope)
   3. [Glossary](#13-glossary)
   4. [References](#14-references)
2. [Overall Description](#2-overall-description)
   1. [General Overview](#21-general-overview)
   2. [Assumptions/Constraints/Risks](#22-assumptionsconstraintsrisks)
      1. [Assumptions](#221-assumptions)
      2. [Constraints](#222-constraints)
      3. [Risks](#223-risks)
3. [System Architecture and Architecture Design](#3-system-architecture-and-architecture-design)
   1. [Architectural Patterns](#31-architectural-patterns)
   2. [Interaction Diagrams](#32-interaction-diagrams)
4. [Detailed Design](#4-detailed-design)
   1. [User Interface Design](#41-user-interface-design)
      1. [Screen Configuration Standardization](#411-screen-configuration-standardization)
      2. [Screen Transition Diagrams](#412-screen-transition-diagrams)
   2. [Data Modeling](#42-data-modeling)
      1. [Conceptual Data Modeling](#421-conceptual-data-modeling)
      2. [Database Design](#422-database-design)
5. [Design Considerations](#5-design-considerations)
   1. [Goals and Guidelines](#51-goals-and-guidelines)
   2. [Architectural Strategies](#52-architectural-strategies)
   3. [Design Principles](#53-design-principles)
   4. [Design Patterns](#54-design-patterns)

---

## 1 Introduction

### 1.1 Objective

The objective of this Software Design Document (SDD) is to provide a comprehensive and detailed description of the software design for the **JAMC (Just A Minor Change)** project. This document serves as a blueprint for the development process, ensuring that the software meets the specified requirements and adheres to best practices in software design and architecture.

This document is intended for:

- Myself (the developer) as a reference during the development process.
- Instructors or mentors who require insight into the design for evaluation purposes.

### 1.2 Scope

The **JAMC** project is a personal web-based educational platform designed to facilitate personalized learning for high school students in Vietnam. The platform enables teachers to create and manage courses, lessons, and educational resources, while students can enroll in courses, track their progress, and engage in discussions through the Q&A module.

This SDD covers:

1. The overall design of the JAMC platform, including system architecture and module decomposition.
2. Detailed designs for user interfaces, data models, class structures, and security mechanisms.
3. Design considerations such as goals, guidelines, architectural strategies, coupling and cohesion, design principles, and design patterns.

### 1.3 Glossary

- **AWS S3**: Amazon Web Services Simple Storage Service, used for file storage.
- **CDN**: Content Delivery Network, a system of distributed servers that deliver web content to users.
- **Component-Based Architecture**: An architectural style that focuses on building software from reusable components.
- **CRUD**: Create, Read, Update, Delete; basic operations for data manipulation.
- **JWT**: JSON Web Token, a compact token format used for secure data transmission.
- **Next.js**: A React framework for building server-side rendered and statically generated web applications.
- **OAuth**: An open standard for access delegation, commonly used for token-based authentication.
- **Prisma**: An ORM (Object-Relational Mapping) tool for Node.js and TypeScript.
- **RBAC**: Role-Based Access Control, a method of regulating access based on user roles.
- **React**: A JavaScript library for building user interfaces.
- **SSR**: Server-Side Rendering.
- **SSG**: Static Site Generation.
- **TLS**: Transport Layer Security, a cryptographic protocol for secure communications.
- **UI**: User Interface.

### 1.4 References

1. Centers for Medicare & Medicaid Services, "System Design Document Template," [Online]. Available: [CMS SDD Template](https://www.cms.gov/Research-Statistics-Data-and-Systems/CMS-Information-Technology/XLC/Downloads/SystemDesignDocument.docx).
2. Software Requirements Specification (SRS) for JAMC Project.
3. Business Requirements Document (BRD) for JAMC Project.
4. Next.js Documentation: [https://nextjs.org/docs](https://nextjs.org/docs).
5. React Documentation: [https://reactjs.org/docs](https://reactjs.org/docs).
6. Prisma Documentation: [https://www.prisma.io/docs](https://www.prisma.io/docs).

---

## 2 Overall Description

### 2.1 General Overview

The **JAMC** platform provides an interactive and personalized learning environment for high school students, allowing teachers to create and manage courses, lessons, and educational resources. Students can enroll in courses, track their progress, and engage in discussions through the Q&A module.

**System and Software Architectures:**

- **Frontend**: Built using **Next.js** and **React**, leveraging component-based architecture for modularity and reusability.
- **Backend**: Utilizes **Next.js server actions** for backend logic, with **Prisma ORM** for database interactions.
- **Database**: **PostgreSQL** managed through **Prisma ORM**.
- **Deployment**: Hosted on **Vercel**, optimized for Next.js applications.
- **File Storage**: Uses **AWS S3** for storing uploaded files.

**Design Goals**:

- **Modularity**: Separation of concerns through reusable components and services.
- **Scalability**: Ability to handle increasing numbers of users and data.
- **Security**: Implementation of robust authentication and authorization mechanisms.
- **Performance**: Optimization through SSR/SSG and efficient data fetching.
- **Usability**: Intuitive and accessible user interfaces.

### 2.2 Assumptions/Constraints/Risks

#### 2.2.1 Assumptions

- **User Access**: Users have access to modern web browsers and stable internet connections.
- **Digital Literacy**: Users possess basic digital skills to navigate the platform.
- **Technical Proficiency**: I have sufficient knowledge in Next.js, React, and Prisma to develop and maintain the project.

#### 2.2.2 Constraints

- **Time Constraints**: Personal project with limited available time.
- **Regulatory Compliance**: Must adhere to Vietnamese data protection laws and GDPR.
- **Technology Stack Limitations**: Restricted to Next.js, PostgreSQL, and Prisma.
- **Deployment Platform**: Vercel is chosen due to optimization with Next.js.
- **Third-Party Dependencies**: Relies on OAuth providers (Google, Facebook) and AWS S3 for file storage.

#### 2.2.3 Risks

- **Security Risks**: Potential data breaches.

  - _Mitigation_: Implement robust security protocols and regular audits.

- **Scalability Risks**: High user load may impact performance.

  - _Mitigation_: Code optimization and scalable solutions if user base grows.

- **Dependency Risks**: Outages or changes in third-party services (e.g., AWS S3, OAuth providers).

  - _Mitigation_: Implement fallback mechanisms and monitor service statuses.

---

## 3 System Architecture and Architecture Design

### 3.1 Architectural Patterns

1. **Component-Based Architecture**

   - **Description**:
     - The application is constructed using reusable components that encapsulate their logic, state, and rendering.
   - **Reason for Choice**:
     - Aligns with React and Next.js methodologies.
     - Facilitates reusability and easier testing.
     - Enhances maintainability and scalability.

2. **Serverless Architecture**

   - **Description**:
     - Uses server actions in Next.js for backend logic that operates without a managed server.
   - **Reason for Choice**:
     - Simplifies deployment and scaling.
     - Reduces operational overhead.

3. **Middleware Pattern**

   - **Description**:
     - Middleware functions process requests before final handlers. Used for tasks like authentication and logging.
   - **Reason for Choice**:
     - Centralizes common functionality.
     - Enhances security and consistency.
     - Reduces code duplication.

### 3.2 Interaction Diagrams

#### 3.2.1 User Registration Sequence Diagram

- **Description**: Illustrates the process of user registration, including form submission, server-side validation, and database storage.

#### 3.2.2 Course Enrollment Sequence Diagram

- **Description**: Shows how a student enrolls in a course, involving UI components, server actions, and database updates.

#### 3.2.3 Question Posting Sequence Diagram

- **Description**: Depicts the steps when a user posts a question, from UI interaction to server processing and storage.

---

## 4 Detailed Design

### 4.1 User Interface Design

#### 4.1.1 Screen Configuration Standardization

- **Layout Consistency**:

  - Standardized header and footer across all pages.
  - Sidebar navigation on dashboard and course pages.

- **Responsive Design**:

  - Mobile-first approach ensuring compatibility across devices.

- **Accessibility**:
  - ARIA labels and semantic HTML for screen readers.

#### 4.1.2

Screen Transition Diagrams

- **User Flow Diagram**: Illustrates user navigation from login to dashboard and other modules.
- **Course Enrollment Flow**: Shows steps from browsing courses to enrollment confirmation.

---

### 4.2 Data Modeling

#### 4.2.1 Conceptual Data Modeling

- **Entities**: `User`, `Course`, `Lesson`, `Enrollment`, `Question`, `Answer`.
- **Relationships**:
  - Users enroll in courses.
  - Courses contain lessons.
  - Users ask questions and provide answers.

#### 4.2.2 Database Design

- **Chosen DBMS**: PostgreSQL
- **Database Diagram**: Includes tables, primary/foreign keys, relationships.
- **Constraints**: `email` unique, with foreign key constraints to ensure referential integrity.

---

## 5 Design Considerations

### 5.1 Goals and Guidelines

- **Modularity**: Design components to be reusable and independent.
- **Scalability**: Ensure the system can handle increased load.
- **Maintainability**: Clean, well-documented code.
- **User Experience**: Prioritize intuitive interfaces.

### 5.2 Architectural Strategies

- **Technology Choice**: **Next.js and React** for web development, **Prisma ORM** for database management.
- **Error Handling**: Global error boundaries in React.
- **State Management**: Use React Hooks and Context API.
- **Performance Optimization**: Code splitting, lazy loading.

### 5.3 Design Principles

- **SOLID Principles**:
  - **Single Responsibility**: Components have one reason to change.
  - **Open/Closed**: Open for extension but closed for modification.
  - **Liskov Substitution**: Subclasses should substitute their base classes.
  - **Interface Segregation**: Client-specific interfaces over a general-purpose one.
  - **Dependency Inversion**: Depend on abstractions, not concretions.

### 5.4 Design Patterns

- **Factory Pattern**: For creating instances of services.
- **Singleton Pattern**: Ensures single instances for services (e.g., `DatabaseService`).
- **Observer Pattern**: Used in event handling mechanisms for real-time updates.

---

This version removes non-architectural patterns while refining the organization around actual architectural elements. Feel free to copy and use it as needed!
