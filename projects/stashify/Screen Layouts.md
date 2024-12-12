## Common Components

### Header Section

- App logo or name (left-aligned)
- User profile icon (right-aligned)
- Notifications or settings icon (optional)

### Footer Navigation

- Navigation bar with main buttons:
  - Home (active)
  - Goals
  - Badges
  - Insights
  - Profile

## Screen Details

### 1. Home Screen

#### Calendar Section

- **Purpose**: Track savings activities on specific dates
- **Views**:
  - **One-Line Calendar**:
    - Compact horizontal weekly view
    - Navigation via arrows/swipe
    - Space-efficient design
  - **Full Calendar**:
    - Monthly grid view
    - Overview of all savings activities
    - More detailed visualization
- **Toggle Button**: Switch between calendar views
- **Date Highlighting**:
  - Green dots for savings contributions
  - Special icons for milestones
- **Savings Details**:
  - Clicking a highlighted date displays a pop-up or side panel showing:
    - Total savings contributed on that day.
    - Breakdown of contributions by goals.
    - Notes associated with contributions (if any).

#### Savings Progress Section

- **Overall Progress**:
  - Total savings progress bar
  - Percentage complete label
- **Active Goals**:
  - Scrollable list/cards
  - Per goal:
    - Name and target amount
    - Progress bar and percentage
    - Deadline countdown
    - "View More" option

#### Badges Preview

- Top badges earned (2-3 displayed)
- Next badge progress indicator

### 2. Create/Edit Goals Screen

#### Purpose

Allow users to create and modify savings goals

#### Components

- **Form Section**:
  - Goal name input
  - Target amount input
  - Deadline selector
  - Category dropdown
  - Notes/images option
- **Preview Section**:
  - Live goal progress visualization
- **Save Button**

### 3. Insights Screen

#### Purpose

Combine detailed goal tracking and financial trends into a single section

#### Components

- **Goal Tracking Section**:
  - **Header**:
    - Goal name
    - Target amount
    - Deadline
  - **Progress Chart**
  - **Milestones** (25%, 50%, 75%)
  - **Actions**:
    - Add contribution
    - Edit goal
    - Delete goal
- **Financial Trends Section**:
  - **Summary Stats**:
    - Total savings
    - Monthly average
  - **Visualizations**:
    - Savings timeline
    - Goal distribution chart
  - **Achievement Highlights**
  - **Time Period Filters**

### 4. Badges and Achievements Screen

#### Purpose

Display user achievements and progress

#### Components

- **Rank Display**
- **Badge Gallery**:
  - Grid layout
  - Earned (colored) and locked (gray) badges
  - Interactive badges with details
- **Achievement Progress**
- **Navigation Controls**

### 5. Add Savings Contribution Screen

#### Contribution Form

- **Elements**:
  - **Amount Field**:
    - Input field for the contribution amount
    - Validation: Ensure the amount is positive and within reasonable limits
  - **Date Selector**:
    - Default: Today’s date
    - Option to select a past date (useful for logging missed updates)
  - **Note Field**:
    - Optional text input for a brief note about the contribution
  - **Save Button**:
    - Prominently displayed for submission

#### Progress Preview

- **Purpose**: Show how the new contribution affects the goal’s progress
- **Elements**:
  - Current progress bar with percentage and target amount (e.g., "50% of \$500")
  - Updated progress preview after contribution

### Integration with Other Screens

1. **From the Goals Screen**:

   - Each goal card includes an "Add Contribution" button.
   - Clicking it opens the "Add Savings Contribution" screen for that goal.

2. **From the Insights Screen**:

   - The goal detail view includes an "Add Contribution" action.
   - The screen updates immediately after a contribution is added.

3. **Calendar Integration**:

   - Contributions made on a specific date appear as events in the calendar view.
   - Clicking a date highlights the contributions for that day, showing:
     - Total amount saved.
     - Goals that received contributions.
     - Notes attached to contributions.


### 6. User Profile Screen

#### Purpose

Allow users to manage their account details and preferences

#### Components

- **Account Information Section**:
  - Display username and email
  - Edit button for updating information (e.g., username, email)
- **Preferences Section**:
  - Toggle notifications on/off
  - Change default calendar view (one-line or full calendar)
- **Security Section**:
  - Change password option
  - Two-factor authentication toggle
- **App Settings Section**:
  - Language selection
  - Theme selection (light/dark mode)
- **Logout Button**:
  - Prominently displayed at the bottom of the screen


