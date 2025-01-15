# **Software Design Document (SDD) for JAMC Project**

## **1. Introduction**

- **Purpose**: The SDD describes the architecture, system components, database schema, API design, and UI flows for the JAMC platform.
- **Scope**: Designed for teachers, students, and admins to manage classes, Q&A, and monetizable learning content.

---

## **2. System Architecture**

### **2.1 High-Level Architecture**

JAMC will use a **full-stack architecture** with **Next.js** for both frontend and backend development. The system will integrate the following components:

1. **Full-Stack Framework**: Next.js (React-based with Server Actions and selective API Routes).
2. **Database**: PostgreSQL, managed using **Prisma ORM** for schema management and query optimization.
3. **Authentication**: OAuth (Google) and JWT-based login for security and user role management.
4. **File Storage**: AWS S3 for storing user-generated content like modules, videos, and documents.
5. **Payment Gateway**: Stripe API for processing payments for monetized courses/modules.
6. **Deployment**: Cloud deployment on AWS or Vercel for scalability and performance.
7. **Caching**: Leveraging **Next.js Automatic Caching** with no current need for Redis.

---

### **2.2 Architecture Discussion**

#### **Server Actions vs API Routes**

- **Server Actions** are the default choice for server-side operations due to their ability to embed backend logic directly into React components. They simplify development, reduce unnecessary API calls, and improve performance.
- **API Routes** will still be used for:
  1. **Payment Integration** (Stripe): Clear separation for payment processing logic.
  2. **External Integrations**: Calls to AI services or third-party tools.

**Decision Rationale**:

- Server Actions simplify server-client interaction for standard data updates (e.g., Q&A submissions).
- API Routes offer greater flexibility when decoupling logic is necessary.

#### **Caching Strategy**

- **Next.js Automatic Caching**: Handles caching of static content and server-rendered pages seamlessly. This reduces the need for external caching tools like Redis at the current scale.
- Redis can be revisited for:
  - Real-time or global shared state (e.g., real-time Q&A prioritization).
  - Expensive computations that require temporary caching.

**Current Decision**: Use Next.js automatic caching for its built-in performance benefits. Redis is deferred until advanced caching needs arise.

#### **State Management**

State management tools handle global states across React components. Options include React Context API, Zustand, and Redux.

- **React Context API**: Used for simple global states like user authentication and role-based access.
- **Zustand or Redux**: To be explored if the state grows in complexity (e.g., managing large-scale real-time Q&A interactions).

**Decision Rationale**:

- Start with React Context API due to its simplicity and suitability for the current scope.
- If performance bottlenecks appear, migrate to **Zustand** for lightweight, scalable state management.

---

### **2.3 System Components**

| Component               | Responsibility                                                                                            |
| ----------------------- | --------------------------------------------------------------------------------------------------------- |
| **User Management**     | Handles registration, login, roles, and profiles.                                                         |
| **Class Management**    | Enables teachers to create, manage, and monitor classes.                                                  |
| **Module Management**   | Allows teachers to upload, organize, and monetize learning resources.                                     |
| **Q&A System**          | Facilitates student-teacher collaboration with questions and answers.                                     |
| **Progress Tracking**   | Tracks student engagement, course progress, and achievements.                                             |
| **Admin Control**       | Content moderation, platform-wide monitoring, and user management.                                        |
| **Payment Processing**  | Manages payments for monetized modules.                                                                   |
| **Notification System** | Sends updates for progress, Q&A activity, and course-related alerts.                                      |
| **AI Integration**      | Enhances Q&A System by providing automated question filtering, answering suggestions, and prioritization. |

---

### **2.4 Component Diagram for Subsystems**

To demonstrate the **component-based architecture** of React.js within the Next.js framework, a **Component Diagram** will be included. This diagram will outline the modular subsystems for:

1. **Frontend React Components**:

   - **Dashboard**: Teacher and student dashboards.
   - **Q&A System**: Interactive question/answer components.
   - **Class Management**: UI components for creating and managing classes.
   - **Module Management**: Components for managing course modules.

2. **Backend with Server Actions and API Routes**:

   - **Server Actions**: Embedded server logic for Q&A submissions, class updates, and module management.
   - **API Routes**: Endpoints for payment integration (Stripe) and external services.

3. **External Services**:

   - **Prisma ORM**: Database queries.
   - **Stripe**: Payment processing.
   - **AWS S3**: File storage integration.
   - **AI Services**: NLP-based automated Q&A suggestions.

This modular component diagram reflects how Next.js supports a component-based frontend architecture while integrating server actions, API routes, and external services seamlessly.

---

## **3. Database Design**

### **3.1 Entity-Relationship Diagram**

Key entities:

1. **User**
2. **StudentProfile**
3. **TeacherProfile**
4. **Course**
5. **Lesson**
6. **Question**
7. **Answer**
8. **Enrollment**
9. **Certificate**

### **3.2 Database Schema**

A detailed schema managed using **Prisma ORM**:

```sql
CREATE TABLE User (
    id UUID PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    role ENUM('STUDENT', 'TEACHER', 'ADMIN'),
    password_hash VARCHAR(255),
    created_at TIMESTAMP DEFAULT NOW()
);

CREATE TABLE Course (
    id UUID PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    description TEXT,
    teacher_id UUID REFERENCES User(id),
    monetized BOOLEAN DEFAULT FALSE,
    created_at TIMESTAMP DEFAULT NOW()
);
```

Prisma will ensure seamless data access and efficient query execution.

---

## **4. Module Flows**

### **4.1 Module Management with Monetization**

**Flow**:

1. **Teacher Logs In**: Authentication via OAuth or JWT.
2. **Teacher Creates a Module**:
   - Inputs details like title, description, and uploads resources (videos, PDFs).
   - System validates and saves data to the database.
3. **Teacher Enables Monetization**:
   - Teacher sets a price for the module.
   - System validates the price and updates the module with `monetized = true`.
4. **Student Purchases Module**:
   - Student initiates purchase (e.g., clicks "Buy Module").
   - System redirects to Stripe's secure payment gateway.
   - Stripe processes the payment and sends confirmation.
5. **System Confirms Payment**:
   - Stripe webhook updates the purchase status in the database.
   - Module access is granted to the student.
6. **Revenue Split**:
   - Platform deducts a commission (e.g., 15%) and transfers the remaining amount to the teacher.
   - Teacher’s dashboard updates earnings and payouts.
7. **Student Accesses Module**:
   - Student can view module resources (videos, PDFs, quizzes).

---

### **4.2 Class Management Flow**

**Flow**:

1. **Teacher Logs In**: Authentication via OAuth or JWT.
2. **Teacher Creates a Class**:
   - Inputs class name, schedule, and description.
   - Associates students by email or unique user ID.
   - System validates and creates the class entry in the database.
3. **Teacher Manages Class**:
   - Tracks student progress (linked to modules).
   - Adds notifications for deadlines, surveys, or updates.
   - Optionally adds survey or assignment links (e.g., Google Forms).
4. **Notification System**:
   - System sends notifications to students about class updates, deadlines, and surveys.
5. **Student Views Class**:
   - Students log in and access class updates and related modules.
   - Students click on shared links (e.g., Google Forms) for surveys or assignments.

---

### **4.3 Q&A System Flow**

**Flow**:

1. **User Logs In**: Authentication via OAuth or JWT.
2. **Student Posts a Question**:
   - Student inputs a title, problem description, and relevant tags.
   - System validates and saves the question to the database.
3. **Teacher/Peer Answers Question**:
   - Users provide answers to the question.
   - System records answers and updates the Q&A database.
4. **Voting on Answers**:
   - Users can upvote or downvote answers.
   - System tallies votes to highlight top answers.
5. **Question Owner Marks Best Answer**:
   - The student who posted the question can mark an answer as the "Best Answer."
   - System updates the question status and notifies the answerer.

---

### **4.4 Progress Tracking Flow**

**Flow**:

1. **Student Logs In**: Authentication via OAuth or JWT.
2. **System Tracks Module/Class Progress**:
   - For modules: System tracks video views, quiz completions, and resource usage.
   - For classes: System tracks attendance and assignment submissions.
3. **Teacher Views Progress**:
   - Teachers access dashboards to see individual and class-wide progress.
   - Data includes percentages of completion, quiz scores, and attendance.
4. **Student Earns Achievements**:
   - System awards badges or certificates based on progress milestones.
   - Achievements are displayed on the student’s profile.

---

