# Flow

### **1. User Registration and Onboarding**:

1. **Teacher Registration and Class Linking**:

   - **Teacher Registration**: Teachers register using their email or school-issued credentials.
   - **Class Creation**:
     - Teachers create their **class on the platform**, linked to their real-time class at school.
     - Each class is assigned a **unique class code**, which students will need to enroll.
   - **Class Management**:
     - Teachers manage enrollment and monitor student progress in the online class that mirrors their real-time course.

2. **Student Registration and Class Enrollment**:

   - **Student Registration**: Students register using email, social accounts, or school-issued credentials.
   - **Class Code Enrollment**:
     - Students provide the **class code** to join the specific class created by their teacher.
     - **Verification Step**: After entering the class code, students are **placed in a pending state** until the teacher **manually verifies** their identity. This ensures that only legitimate students gain access.
     - Teachers will receive a notification or dashboard prompt to approve or reject students who attempt to join with the class code.

3. **Unified Classroom Experience**:
   - **Synchronized Learning**:
     - Once verified, students follow the class schedule set by the teacher, ensuring that everyone stays on the same page in both the real-time and online class environments.
   - **Personalization**: Students receive personalized recommendations and additional resources if they are flagged as needing extra support or if they are excelling beyond the class pace.

---

### **2. Course Enrollment**:

- **Flow**:

  - **Free Access**: Students automatically gain access to their **class teacher’s course** based on their school enrollment.
  - **Paid Access**: Students can browse additional courses taught by other teachers, using the **rating system** and AI recommendations to guide their choice. Payment is required for these external courses.
  - **AI Recommendation**: The system suggests courses based on student preferences and the teacher's course rating.

- **Key Data**:
  - **Courses**: `course_id`, `title`, `description`, `teacher_id`, `rating`
  - **Enrollments**: `student_id`, `course_id`, `access_type (free/paid)`

---

### **3. Course Content and Progression**:

- **Flow**:
  - Once enrolled, students access course content at their own pace, which includes:
    - **Video lessons**.
    - **Supplementary materials** (PDFs, links).
    - **Quizzes and Assignments** after each lesson.
  - **Milestones**: Each course has defined **milestones** that align with the school schedule (e.g., one lesson per week), ensuring students stay on track.
  - **Progress Monitoring**: Students’ progress is tracked, and the system flags students who fall behind or speed ahead.
    - **Flagging Slower/Faster Learners**: AI analyzes progress. If students slow down or speed up too much, the teacher is notified.
- **Key Data**:
  - **Lessons**: `lesson_id`, `course_id`, `content`, `video_url`
  - **Quizzes**: `quiz_id`, `lesson_id`, `questions`, `correct_answers`
  - **Progress**: `student_id`, `course_id`, `lesson_completion`, `quiz_results`, `flagged_status`

---

### **4. Student Grouping (Faster/Slower Learners)**:

- **Flow**:

  - **Grouping**: Students are grouped based on learning pace.
    - **Faster learners** and **slower learners** can be placed in the same group to foster collaboration.
    - Group assignments ensure that students who excel can help peers, which promotes peer learning and engagement.
  - **Flagging**: The system flags students who have slowed down in their progression. Teachers are notified, and these students are placed into a group for additional support from peers or direct teacher interaction.
  - **Teacher Response**: Teachers receive reports on flagged students and can intervene, providing personalized feedback or extra learning resources.

- **Key Data**:
  - **Groups**: `group_id`, `student_ids (faster and slower learners)`, `group_type`
  - **Flags**: `student_id`, `flagged_reason (slow_progress/fast_progress)`, `group_assigned`

---

### **5. AI-Driven Recommendations and Question Filtering**:

- **Flow**:

  - **AI Question Filtering**: During the learning process, students can ask questions in the Q&A section. AI **filters** and **prioritizes** the most relevant questions, ensuring the teacher spends time on the most insightful or common issues.
  - **AI Course Recommendations**: AI recommends additional courses to students based on their progress and course ratings.
    - Faster learners may receive recommendations for more advanced or complementary courses.
    - Slower learners may be recommended revision courses or additional materials to help them catch up.

- **Key Data**:
  - **Questions**: `question_id`, `student_id`, `content`, `lesson_id`, `priority_score`
  - **Recommendations**: `student_id`, `recommended_courses`

---

### **6. Credit Points and Engagement**:

- **Flow**:

  - **Credit Points System**:
    - Students earn **credit points** by:
      - Asking high-quality questions (upvoted by peers/teachers).
      - Answering questions on discussion boards.
      - Completing quizzes and assignments on time.
    - **Milestone-Based Credits**: Additional credit points are awarded when students reach specific milestones within the course.
  - **Teacher’s Use of Credit Points**: Teachers use credit points to evaluate student engagement, providing formative assessments that contribute to the overall understanding of a student's progress.

- **Key Data**:
  - **Credit Points**: `student_id`, `earned_points`, `earned_for (questions, answers, quizzes)`
  - **Upvotes**: `question_id`, `upvote_count`

---

### **7. Rating System for Teachers and Courses**:

- **Flow**:

  - **Student Ratings**: After completing lessons or courses, students rate the content based on the quality, clarity, and engagement level of the teacher.
  - **AI-Driven Ranking**: Based on these ratings, AI ranks the courses and teachers, prioritizing highly rated teachers in future recommendations.
    - **Low-Rated Courses**: Courses that consistently receive low ratings will be less visible in the system, encouraging teachers to improve content quality.

- **Key Data**:
  - **Ratings**: `student_id`, `course_id`, `rating (1-5)`
  - **Ranking**: `course_id`, `rating_average`

---

### **8. Teacher Dashboard and Analytics**:

- **Flow**:

  - Teachers have access to an **analytics dashboard** showing:
    - **Student progress**: Overview of each student’s lesson completion, quiz scores, and flagged students (faster/slower learners).
    - **Engagement metrics**: Credit points earned, questions asked, and overall participation.
  - **Intervention Alerts**: The system alerts teachers to students who have been flagged for slow or fast progression, allowing them to intervene with feedback or additional resources.

- **Key Data**:
  - **Teacher Analytics**: `teacher_id`, `course_id`, `student_progress`, `student_engagement`, `flags`

---

### **9. Progress Review and Certificates**:

- **Flow**:

  - **Student Progress**: Students can review their learning milestones, quiz scores, and earned credit points in their personal dashboard.
  - **Certificates and Badges**: Upon course completion or milestone achievements, students receive **certificates** or **badges**. These rewards are displayed on the student’s profile and can be shared publicly.

- **Key Data**:
  - **Certificates**: `student_id`, `course_id`, `achievement (certificate/badge)`

---

### **10. Revenue Model for Teachers**:

- **Flow**:

  - Teachers earn revenue based on **student enrollments** outside their official class.
  - Courses with high ratings attract more students, leading to increased income for the teacher.
  - **Subscription Model**: There could also be a subscription service for students to access multiple courses from different teachers, with revenue distributed based on student engagement.

- **Key Data**:
  - **Revenue**: `teacher_id`, `course_id`, `earned_amount`, `student_enrollment`

---

### **Final Notes**:

- The system continuously tracks student progress and adjusts recommendations and flags accordingly.
- AI plays a central role in managing student engagement and teacher workload, ensuring that students receive the support they need while teachers focus on high-priority tasks.
- Credit points and ratings drive competition and quality improvement among both students and teachers.
