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
   3. [Analysis Class Diagrams](#33-analysis-class-diagrams)
   4. [Unified Analysis Class Diagram](#34-unified-analysis-class-diagram)
   5. [Security Software Architecture](#35-security-software-architecture)
4. [Detailed Design](#4-detailed-design)
   1. [User Interface Design](#41-user-interface-design)
      1. [Screen Configuration Standardization](#411-screen-configuration-standardization)
      2. [Screen Transition Diagrams](#412-screen-transition-diagrams)
      3. [Screen Specifications](#413-screen-specifications)
   2. [Data Modeling](#42-data-modeling)
      1. [Conceptual Data Modeling](#421-conceptual-data-modeling)
      2. [Database Design](#422-database-design)
         1. [Database Management System](#4221-database-management-system)
         2. [Database Diagram](#4222-database-diagram)
         3. [Database Detail Design](#4223-database-detail-design)
   3. [Non-Database Management System Files](#43-non-database-management-system-files)
   4. [Class Design](#44-class-design)
      1. [General Class Diagram](#441-general-class-diagram)
      2. [Class Diagrams](#442-class-diagrams)
      3. [Class Design](#443-class-design)
5. [Design Considerations](#5-design-considerations)
   1. [Goals and Guidelines](#51-goals-and-guidelines)
   2. [Architectural Strategies](#52-architectural-strategies)
   3. [Coupling and Cohesion](#53-coupling-and-cohesion)
   4. [Design Principles](#54-design-principles)
   5. [Design Patterns](#55-design-patterns)

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

The document does not cover implementation details, testing procedures, or deployment configurations unless they directly impact the design.

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
- **Server Actions**: Next.js feature for handling server-side logic within components.
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

The **JAMC** platform aims to provide an interactive and personalized learning environment for high school students. It allows teachers to create and manage courses, lessons, and educational resources, while students can enroll in courses, track their progress, and engage in discussions through the Q&A module.

**System and Software Architectures:**

- **Frontend:** Built using **Next.js** and **React**, leveraging component-based architecture for modularity and reusability.
- **Backend:** Utilizes **Server Actions** in Next.js for server-side logic, with **Prisma ORM** for database interactions.
- **Database:** **PostgreSQL** database managed through **Prisma ORM**.
- **Deployment:** Hosted on **Vercel**, optimized for Next.js applications.
- **File Storage:** Uses **AWS S3** for storing uploaded files.

**Design Goals:**

- **Modularity:** Separation of concerns through reusable components and services.
- **Scalability:** Ability to handle increasing numbers of users and data.
- **Security:** Implementation of robust authentication and authorization mechanisms.
- **Performance:** Optimization through SSR/SSG and efficient data fetching.
- **Usability:** Intuitive and accessible user interfaces.

### 2.2 Assumptions/Constraints/Risks

#### 2.2.1 Assumptions

- **User Access:** Users have access to modern web browsers and stable internet connections.
- **Digital Literacy:** Users possess basic digital skills to navigate the platform.
- **Technical Proficiency:** I have sufficient knowledge in Next.js, React, and Prisma to develop and maintain the project.

#### 2.2.2 Constraints

- **Time Constraints:** As a personal project, time management is crucial to complete the project within the desired timeframe.
- **Regulatory Compliance:** Must adhere to Vietnamese data protection laws and GDPR.
- **Technology Stack Limitations:** Restricted to Next.js, PostgreSQL, and Prisma as per project requirements.
- **Deployment Platform:** Must use Vercel for deployment due to optimization with Next.js.
- **Third-Party Dependencies:** Reliance on OAuth providers (Google, Facebook) and AWS S3 for file storage.

#### 2.2.3 Risks

- **Security Risks:** Potential for data breaches if security measures are insufficient.

  - _Mitigation:_ Implement robust security protocols and regular audits.

- **Scalability Risks:** High user load may impact performance.

  - _Mitigation:_ Optimize code for performance and consider scalable solutions if user base grows.

- **Dependency Risks:** Outages or changes in third-party services (e.g., AWS S3, OAuth providers).

  - _Mitigation:_ Implement fallback mechanisms and monitor service statuses.

- **Data Loss Risks:** Potential loss of data due to system failures.

  - _Mitigation:_ Regular backups and database redundancy.

---

## 3 System Architecture and Architecture Design

### 3.1 Architectural Patterns

#### Chosen Architectural Patterns

1. **Component-Based Architecture**

   - **Description:**

     - The application is constructed using reusable components that encapsulate their own logic, state, and rendering.
     - Components are the fundamental building blocks, allowing for modular and maintainable code.

   - **Reason for Choice:**

     - Aligns with React and Next.js methodologies.
     - Facilitates reusability and easier testing.
     - Enhances maintainability and scalability.

2. **Server-Side Rendering (SSR) and Static Site Generation (SSG)**

   - **Description:**

     - **SSR:** Pages are rendered on the server at request time.
     - **SSG:** Pages are pre-rendered at build time, resulting in static HTML files.

   - **Reason for Choice:**

     - Improves performance and user experience.
     - Enhances SEO by providing fully rendered pages to search engines.
     - Balances dynamic content needs with performance optimization.

3. **Serverless Architecture**

   - **Description:**

     - Utilizes Next.js **Server Actions** for backend logic.
     - Code executes in response to events without managing server infrastructure.

   - **Reason for Choice:**

     - Simplifies deployment and scaling.
     - Reduces operational overhead.
     - Leverages cloud services effectively.

4. **React Hooks and Context API**

   - **Description:**

     - **React Hooks:** Functions like `useState`, `useEffect`, `useContext` for state and side-effect management.
     - **Context API:** Allows for global state sharing without prop drilling.

   - **Reason for Choice:**

     - Simplifies state management.
     - Encourages functional programming.
     - Enhances code readability and maintainability.

5. **Middleware Pattern**

   - **Description:**

     - Middleware functions process requests before reaching final handlers.
     - Used for authentication, authorization, logging, and validation.

   - **Reason for Choice:**

     - Centralizes common functionality.
     - Enhances security and consistency.
     - Reduces code duplication.

### 3.2 Interaction Diagrams

_Placeholder for Interaction Diagrams_

#### 3.2.1 User Registration Sequence Diagram

- **Description:** Illustrates the process of user registration, including form submission, server-side validation, and database storage.

- _[Diagram to be added]_

#### 3.2.2 Course Enrollment Sequence Diagram

- **Description:** Shows how a student enrolls in a course, involving UI components, server actions, and database updates.

- _[Diagram to be added]_

#### 3.2.3 Question Posting Sequence Diagram

- **Description:** Depicts the steps when a user posts a question, from UI interaction to server processing and storage.

- _[Diagram to be added]_

### 3.3 Analysis Class Diagrams

_Placeholder for Analysis Class Diagrams_

#### 3.3.1 User Management Module

- **Components:**

  - `UserComponent`
  - `ProfileComponent`
  - `AuthenticationService`
  - `AuthorizationService`
  - `AuthenticatorComponent`

- _[Diagram to be added]_

#### 3.3.2 Course Management Module

- **Components:**

  - `CourseComponent`
  - `LessonComponent`
  - `EnrollmentComponent`
  - `ProgressComponent`
  - `CourseService`

- _[Diagram to be added]_

#### 3.3.3 Q&A Module

- **Components:**

  - `QuestionComponent`
  - `AnswerComponent`
  - `CommentComponent`
  - `VoteComponent`
  - `QnAService`

- _[Diagram to be added]_

### 3.4 Unified Analysis Class Diagram

_Placeholder for Unified Analysis Class Diagram_

- **Description:** Combines all components and services from individual modules, showing relationships and interactions.

- _[Diagram to be added]_

### 3.5 Security Software Architecture

#### 1. Authentication

- **Mechanisms Used:**

  - **OAuth 2.0 Integration** with Google and Facebook.
  - **Email/Password Authentication** with secure password storage (bcrypt).
  - **Multi-Factor Authentication (MFA)** for enhanced security.

- **Components:**

  - `AuthenticationService`
  - `AuthenticatorComponent`
  - `SessionManagement`

#### 2. Authorization

- **Role-Based Access Control (RBAC):**

  - **Roles:**

    - `ONBOARDING`, `STUDENT`, `TEACHER`, `ADMIN`.

  - **Permissions:**

    - Managed by `AuthorizationService`.
    - Enforced via middleware and component-level checks.

#### 3. Encryption Protocol

- **Data in Transit:**

  - TLS/HTTPS encryption for all client-server communications.

- **Data at Rest:**

  - Encryption of sensitive data in the database.
  - Secure storage on AWS S3 with pre-signed URLs and access policies.

#### 4. Logging and Auditing Design

- **Activity Logging:**

  - Logs critical actions like authentication attempts and data modifications.

- **Auditing:**

  - Regular review of logs for compliance and security monitoring.

#### 5. Security Measures Summary

- **Secure Coding Practices:**

  - Input validation and sanitization.
  - Use of environment variables for sensitive data.

- **Regular Updates:**

  - Keeping dependencies and libraries up to date.

- **Incident Response Plan:**

  - Procedures for handling security incidents.

---

## 4 Detailed Design

### 4.1 User Interface Design

#### 4.1.1 Screen Configuration Standardization

- **Layout Consistency:**

  - Standardized header and footer across all pages.
  - Sidebar navigation on dashboard and course pages.

- **Responsive Design:**

  - Mobile-first approach ensuring compatibility across devices.

- **Accessibility:**

  - ARIA labels and semantic HTML for screen readers.
  - Keyboard navigation support.

#### 4.1.2 Screen Transition Diagrams

_Placeholder for Screen Transition Diagrams_

- **Diagram Descriptions:**

  - **User Flow Diagram:** Illustrates user navigation from login to dashboard and other modules.

  - **Course Enrollment Flow:** Shows steps from browsing courses to enrollment confirmation.

- _[Diagrams to be added]_

#### 4.1.3 Screen Specifications

_Include screen images and descriptions_

- **Login Screen:**

  - Fields: Email, Password.

  - Buttons: Login, OAuth Login Options.

- **Dashboard:**

  - Sections: Enrolled Courses, Notifications, Progress Overview.

- **Course Page:**

  - Information: Course Details, Lessons List, Instructor Info.

- **Q&A Page:**

  - Features: Question List, Search Bar, Ask Question Button.

### 4.2 Data Modeling

#### 4.2.1 Conceptual Data Modeling

_Placeholder for E-R Diagram_

- **Entities:**

  - `User`, `Course`, `Lesson`, `Enrollment`, `Question`, `Answer`, `Group`, `Revenue`.

- **Relationships:**

  - Users enroll in courses.

  - Courses contain lessons.

  - Users ask questions and provide answers.

- _[E-R Diagram to be added]_

#### 4.2.2 Database Design

##### 4.2.2.1 Database Management System

- **Chosen DBMS:** PostgreSQL

- **Description:**

  - Open-source relational database.

  - Supports complex queries and transactions.

  - Integrates well with Prisma ORM.

##### 4.2.2.2 Database Diagram

_Placeholder for Database Schema Diagram_

- **Diagram Includes:**

  - Tables, columns, data types.

  - Primary keys, foreign keys.

  - Relationships between tables.

- _[Database Diagram to be added]_

##### 4.2.2.3 Database Detail Design

**Example Table Design:**

**Table: User**

| #   | PK  | FK  | Column Name | Data Type  | Default Value | Mandatory | Description                    |
| --- | --- | --- | ----------- | ---------- | ------------- | --------- | ------------------------------ |
| 1   | X   |     | id          | UUID       |               | Yes       | Unique identifier for the user |
| 2   |     |     | name        | String     |               | Yes       | User's full name               |
| 3   |     |     | email       | String     |               | Yes       | User's email address           |
| 4   |     |     | password    | String     |               | Yes       | Hashed password                |
| 5   |     |     | role        | Enum(Role) | 'ONBOARDING'  | Yes       | User's role in the system      |
| 6   |     |     | createdAt   | DateTime   | NOW()         | Yes       | Account creation timestamp     |
| 7   |     |     | updatedAt   | DateTime   | NOW()         | Yes       | Last update timestamp          |

**Additional Details:**

- **Indexes:** Create indexes on frequently queried fields like `email` and `role`.

- **Constraints:**

  - `email` must be unique.

  - Foreign key constraints to ensure referential integrity.

**Database Script:**

_Include SQL scripts for table creation and constraints._

### 4.3 Non-Database Management System Files

- **Configuration Files:**

  - `next.config.js`: Next.js configuration settings.

  - `.env`: Environment variables for sensitive data.

- **Usage:**

  - Input for application configuration.

  - Read by the application at startup.

- **Access Method:**

  - Read-only access at runtime.

- **Backup and Recovery:**

  - Regular backups of configuration files.

  - Secure storage with restricted access.

### 4.4 Class Design

#### 4.4.1 General Class Diagram

_Placeholder for General Class Diagram_

- **Description:**

  - Shows all classes/components in the system.

  - Organized into packages or modules.

- _[Diagram to be added]_

#### 4.4.2 Class Diagrams

##### 4.4.2.1 Class Diagram for User Module

_Placeholder for User Module Class Diagram_

- **Classes:**

  - `UserComponent`

  - `ProfileComponent`

  - `AuthenticationService`

  - `AuthorizationService`

- _[Diagram to be added]_

##### 4.4.2.2 Class Diagram for Course Module

_Placeholder for Course Module Class Diagram_

- **Classes:**

  - `CourseComponent`

  - `LessonComponent`

  - `EnrollmentComponent`

  - `CourseService`

- _[Diagram to be added]_

#### 4.4.3 Class Design

##### 4.4.3.1 Class `UserComponent`

**UML Diagram:**

_Placeholder for `UserComponent` UML Diagram_

**Attributes:**

| #   | Name       | Data Type | Default Value | Description                |
| --- | ---------- | --------- | ------------- | -------------------------- |
| 1   | userData   | Object    | {}            | Stores user information    |
| 2   | isLoggedIn | Boolean   | false         | User authentication status |

**Operations:**

| #   | Name           | Return Type | Description                |
| --- | -------------- | ----------- | -------------------------- |
| 1   | render()       | JSX Element | Renders the user component |
| 2   | handleLogin()  | void        | Handles user login         |
| 3   | handleLogout() | void        | Handles user logout        |

**Methods:**

- **handleLogin():**

  - Parameters: `credentials` (Object)

  - Validates input and calls `AuthenticationService`.

  - Updates `isLoggedIn` status upon success.

- **handleLogout():**

  - Clears user data and updates `isLoggedIn` status.

**State:**

- Uses React state hooks to manage `userData` and `isLoggedIn`.

##### 4.4.3.2 Class `CourseComponent`

**UML Diagram:**

_Placeholder for `CourseComponent` UML Diagram_

**Attributes:**

| #   | Name       | Data Type | Default Value | Description               |
| --- | ---------- | --------- | ------------- | ------------------------- |
| 1   | courseData | Object    | {}            | Stores course information |
| 2   | isEnrolled | Boolean   | false         | Enrollment status of user |

**Operations:**

| #   | Name              | Return Type | Description                  |
| --- | ----------------- | ----------- | ---------------------------- |
| 1   | render()          | JSX Element | Renders the course component |
| 2   | enrollInCourse()  | void        | Enrolls user in the course   |
| 3   | fetchCourseData() | void        | Retrieves course information |

**Methods:**

- **enrollInCourse():**

  - Checks if the user is eligible to enroll.

  - Calls server action to enroll the user.

  - Updates `isEnrolled` status upon success.

- **fetchCourseData():**

  - Retrieves course details from the server.

  - Updates `courseData` state.

**State:**

- Manages state using React hooks for `courseData` and `isEnrolled`.

---

## 5 Design Considerations

### 5.1 Goals and Guidelines

- **Modularity:** Design components to be reusable and independent.

- **Scalability:** Ensure the system can handle increased load without performance degradation.

- **Maintainability:** Write clean, well-documented code following best practices.

- **User Experience:** Prioritize intuitive and accessible interfaces.

### 5.2 Architectural Strategies

- **Technology Choice:**

  - **Next.js and React** for modern web development.

  - **Prisma ORM** for database interactions.

- **Reusability:**

  - Utilize existing libraries and components where appropriate.

- **Error Handling:**

  - Implement global error boundaries in React.

  - Use try-catch blocks in server actions.

- **State Management:**

  - Use React Hooks and Context API.

- **Performance Optimization:**

  - Implement code splitting and lazy loading.

  - Optimize images and assets.

### 5.3 Coupling and Cohesion

- **Coupling:**

  - Achieved low coupling by ensuring components communicate through well-defined interfaces.

  - Used dependency injection for services to reduce direct dependencies.

- **Cohesion:**

  - High cohesion within components; each component has a single, well-defined purpose.

- **Proofs:**

  - Components like `UserComponent` handle only user-related functionality.

  - Services like `AuthenticationService` are dedicated to authentication logic.

### 5.4 Design Principles

- **SOLID Principles:**

  - **Single Responsibility:** Components and classes have one reason to change.

  - **Open/Closed:** Open for extension but closed for modification.

  - **Liskov Substitution:** Subclasses should be substitutable for their base classes.

  - **Interface Segregation:** Many client-specific interfaces are better than one general-purpose interface.

  - **Dependency Inversion:** Depend on abstractions, not concretions.

- **Application:**

  - Designed components to be easily extendable without modifying existing code.

  - Used interfaces and abstract classes where appropriate.

### 5.5 Design Patterns

- **Factory Pattern:**

  - Used for creating instances of services like `AuthenticationService`.

- **Singleton Pattern:**

  - Ensured only one instance of certain services exists (e.g., `DatabaseService`).

- **Observer Pattern:**

  - Implemented in event handling mechanisms for real-time updates.

- **Implementation Details:**

  - **Factory Pattern:** Created factory functions to instantiate services based on configuration.

  - **Singleton Pattern:** Used static variables and methods to maintain a single instance.

  - **Observer Pattern:** Utilized event emitters to notify components of changes.

---