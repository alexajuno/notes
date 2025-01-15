## Use Cases

### **Use Case 1: Create and Manage Savings Goals**
- **Description**: The user creates specific savings goals and manages them over time.
- **Steps**:
  1. User selects "Create a New Goal."
  2. User enters details (goal name, target amount, deadline, optional image/icon).
  3. System calculates daily/weekly/monthly savings recommendations based on the deadline.
  4. User views and edits goals from the "Goals" section.
- **Extensions**:
  - Option to categorize goals (e.g., personal, travel, emergency).
  - Attach motivational notes or images to goals.

---

### **Use Case 2: Track Savings Progress**
- **Description**: The user tracks their progress toward savings goals using visual aids.
- **Steps**:
  1. System updates progress based on user input (amount saved so far).
  2. User views progress charts or timelines for each goal.
  3. System highlights milestones achieved (e.g., 50% completion).
- **Extensions**:
  - Provide weekly/monthly summary reports.
  - Option to export progress reports (e.g., PDF).

---

### **Use Case 3: Receive Notifications and Motivational Prompts** [Optional]
- **Description**: The system keeps users engaged through notifications.
- **Steps**:
  1. System sends reminders based on the user's schedule (e.g., "Save $10 today!").
  2. System sends motivational messages when progress is made (e.g., "You're halfway there!").
  3. System notifies users of inactivity (e.g., "You haven't updated your savings for a week").
- **Extensions**:
  - Tailor notifications to user preferences (frequency, tone, time of day).

---

### **Use Case 4: Earn Rewards Through Gamification**
- **Description**: Users earn badges, points, or unlock content as they achieve savings milestones.
- **Steps**:
  1. System awards badges for specific achievements (e.g., "First Goal Achieved").
  2. System updates user's progress level based on points earned.
  3. User views their badges and achievements in the "Achievements" section.
- **Extensions**:
  - Unlock themed content or features as rewards.
  - Share achievements on social media.

---

### **Use Case 5: Set Up Personalization and Preferences**
- **Description**: The user customizes their app experience for better usability.
- **Steps**:
  1. User selects preferences for notifications, themes, and savings goal categories.
  2. System saves preferences and adjusts accordingly.
  3. User reviews insights tailored to their savings behavior.
- **Extensions**:
  - Change themes (e.g., light/dark mode).
  - Add personal savings tips or notes.

---

### **Use Case 6: Access Financial Education Resources**
- **Description**: The app provides learning materials or tips to support financial literacy.
- **Steps**:
  1. User accesses the "Resources" section from the navigation bar.
  2. System displays curated articles, videos, or quizzes.
  3. User bookmarks favorite resources or shares them.
- **Extensions**:
  - Offer insights based on user behavior (e.g., saving tips for overspenders).

---

### **Use Case 7: View and Analyze Overall Savings Statistics**
- **Description**: The user views aggregated data for all savings goals.
- **Steps**:
  1. System aggregates savings data across all goals.
  2. User accesses the "Statistics" section to review overall progress.
  3. System provides insights (e.g., "You've saved 30% more this month!").
- **Extensions**:
  - Allow exporting or sharing overall progress.
  - Compare progress across months or years.

### **Use Case 8: View and Manage Badge Collection**
- **Actors**: User, System
- **Description**: The user can view their badge collection, including progress and ranks. Badges may be predefined or tied to specific goals.
- **Steps**:
  1. User accesses the “Badges and Achievements” section from the navigation menu.
  2. System displays:
     - Earned badges with descriptions.
     - Badge progress for ongoing achievements.
     - User’s rank or level based on badge accomplishments.
  3. User clicks on a badge to view details (e.g., how it was earned, related goals).
  4. System updates badge progress or awards new badges as goals are completed.
- **Extensions**:
  - Add functionality for predefined badges, such as:
    - “First Goal Set”
    - “Consistency Master” (saving for 7 days in a row)
    - “Milestone Achiever” (completing 50% of a goal).
  - Option to sort or filter badges (e.g., by rank, category, or progress).
  - Display leaderboards based on badges for a social or competitive element.

You're absolutely right! Without a way for users to input their savings contributions, the system cannot track progress effectively. Let's address this with a new **use case** and corresponding screen layout for adding savings contributions.

---

### **Use Case 9: Add Savings Contribution**
- **Actors**: User, System
- **Description**: The user inputs an amount to contribute toward a specific savings goal. The system updates the goal's progress accordingly.
- **Steps**:
  1. User selects a goal from the "Goals" or "Track Progress" screen.
  2. User clicks "Add Contribution."
  3. System displays a form to enter:
     - Contribution amount.
     - Date of the contribution (default: today).
     - Optional note (e.g., “Saved from freelance gig”).
  4. User submits the form.
  5. System validates and updates the goal's progress bar and overall savings statistics.
  6. System confirms with a success message or animation.
- **Extensions**:
  - Allow adding multiple contributions at once.
  - Option to edit or delete previous contributions.

---

## Discussion Zone

- A section for displaying badges according to the goals. When the user create a new goal, a new badge will also be created accordingly.
    - I'm not sure about this part. Is it suitable for badges and achievements to be created on the fly? Or predefined badges and achievements? I think predefined badges and achievements are better and most developers will choose this way.
    - The section I'm thinking of would need to display ranks, some badge progresses, and something else I don't remember lol.

### Consideration for **Dynamic vs. Predefined Badges**
While dynamic badge creation tied to user goals might seem engaging, it has some drawbacks:
- **Complexity**: Dynamically generated badges could lead to cluttered or less meaningful achievements.
- **Predefined Badges Advantage**: Predefined badges are easier to design, visually appealing, and allow developers to control the badge ecosystem (e.g., ranks, progression flow).

We could use a **hybrid approach**:
- Have a set of predefined badges for major achievements.
- Optionally create “goal-specific” badges, but restrict these to visually simple icons tied to user-defined goals, keeping them separate from main achievements.

### Screen Representation of Badges
This would translate into a **Badges and Achievements** screen with:
- A **Rank Display**: Highlighting the user’s rank or level based on badge count.
- **Badge Progress Indicators**: Showing progress for partially completed badges (e.g., “80% of Consistency Master”).
- **Badge List/Icons**:
  - Earned badges are displayed in full color with descriptions.
  - Locked badges are grayed out with hints for unlocking them.

### Discussion on notifications

- For a free, modern and minimalist app, I think notifications are not necessary.

### Discussion on the learnability

- Given the idea of minimalism of this app, I wonder if later on, the user's needs grow complex, and the app needs to be more customizable and might want more use cases, will that be a problem?
  - I know the stakeholder of this app and I don't think he will take this into account

