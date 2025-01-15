Below is a revised set of documents incorporating the stakeholder changes and additional considerations. Unwanted features (like daily targets) have been excluded per your direction. Ambiguous points (like “spend” stashes) are reasoned out to align with typical financial management patterns. The concept of user-defined rewards and badges is simplified to maintain coherence and stability. Finally, a preliminary wireframe design file is included, referencing Apple’s Human Interface Guidelines.

---

# Revised Documents

## Description

### Context & Problem  
Young adults often struggle to form positive financial habits and maintain consistent savings toward their long-term goals. Existing financial management solutions can be too complex, uninspiring, or lacking in personalization. This project aims to simplify the process of setting financial targets and tracking progress, making it more engaging and user-driven.

### Proposed Solution: Stashify  
**Stashify** is a mobile application focusing on guiding users toward their financial targets in a minimalist, user-friendly manner. Instead of pushing daily targets, it provides monthly savings goals, allowing users to update their stash contributions at their convenience. A “stash” represents a category or goal—users may save money into stashes (like a travel fund) or track spending-related categories to keep expenses in check. The interface blends progress tracking, badges, and minimal gamification to keep users motivated without overwhelming complexity.

### Key Principles  
- **Simplicity & Minimalism:** Focus on intuitive navigation, clean visuals, and minimal clutter.  
- **Personalization:** Users can set their own stashes, define monthly targets, and even specify a personal reward they’ll claim upon completion of a stash.  
- **Positive Reinforcement:** Celebrating achievements through badges, ranks, and custom rewards encourages long-term engagement.

### Differentiators  
- **Flexible Stashes:** Users define categories (“stashes”) for both saving (putting money aside) and controlled spending (tracking how much they allocate before hitting a certain limit).  
- **User-Defined Rewards & Achievements:** Upon completing a stash, users unlock a system-generated badge and their own pre-defined reward (e.g., a small personal treat), providing a tangible sense of accomplishment.  
- **Ranking & Gamification:** Accumulating completed stashes contributes to a ranking system, instilling a sense of progression and status in the user community.

---

## Use Cases

### Use Case 1: Create and Manage Stashes  
**Description:** Users create stashes representing financial goals or categories. Each stash has a target amount to save or spend within a month, and a defined reward upon completion.  
**Steps:**  
1. User selects “New Stash” (pop-up or button on the home screen).  
2. User inputs:  
   - Stash name (e.g., “Vacation Fund” or “Dining Out Budget”)  
   - Type (Save or Spend)  
   - Monthly target amount  
   - Final goal (if any) and associated custom reward (e.g., “Buy yourself a new book” after completing the vacation fund goal).  
   - Notification preferences for reminders.  
3. System saves the stash, initializes progress at 0%, and integrates it into statistics and badges tracking.  
**Extensions:**  
- Categorize stashes (e.g., Travel, Essentials, Entertainment).  
- Edit stash details or targets at any time.

### Use Case 2: Add Contributions or Expenses  
**Description:** Users update a stash’s progress by adding money saved or recorded spending.  
**Steps:**  
1. User selects a stash from the home or statistics screen.  
2. User taps “Add Entry” to either contribute saved money or record spending against that stash.  
3. User inputs amount and date; optional note (e.g., “Freelance earnings” or “Dinner out”).  
4. System updates stash progress, reflecting how close the user is to their monthly goal.  
**Extensions:**  
- Allow editing or deleting past entries.  
- Provide quick-add shortcuts for frequently used amounts.

### Use Case 3: Track Monthly Progress & Statistics  
**Description:** Users view overall statistics to understand how stashes are performing.  
**Steps:**  
1. User opens the “Statistics” screen.  
2. System displays a list of all stashes (both saving and spending types) and their completion percentages for the current month.  
3. User can filter or toggle between “All,” “In-Progress,” and “Completed” stashes for clarity.  
4. System provides monthly summaries, comparisons to previous months, and insights (e.g., “You’re at 75% of your Vacation Fund target!”).  
**Extensions:**  
- Export monthly summary as PDF.  
- Compare multiple months or categories side-by-side.

### Use Case 4: Achievements & Badges  
**Description:** Users earn badges when they fully complete a stash’s monthly goal. A completed stash automatically generates a “Completed Badge” and the user can redeem their predefined personal reward.  
**Steps:**  
1. Upon reaching the monthly target for a stash, system triggers a “Receive Badge” pop-up.  
2. The badge is saved in the “Achievements” section under “Completed”.  
3. User views badges in two segments:  
   - **In-Progress:** Stashes currently being worked on.  
   - **Completed:** Stashes fully achieved this month.  
4. User’s completed stashes add points toward a rank or level system.  
**Extensions:**  
- Add filters or sorting in the badge gallery.  
- View user’s overall rank and progress toward next level.

### Use Case 5: Notifications & Personalization  
**Description:** Users set preferences for reminders and notifications.  
**Steps:**  
1. User adjusts notification frequency (e.g., weekly reminders to add contributions, monthly summary notifications).  
2. System tailors motivational messages and reminders accordingly.  
3. User can select themes (light/dark mode) and language preferences.  
**Extensions:**  
- Integrate subtle tips or financial insights based on user behavior.

---

## Screen Layouts (High-Level)

### Home Screen  
- **Monthly Targets Overview:** Show a summary of total progress across all stashes for the month.  
- **Stash List (In-Progress):** Display active stashes with progress bars.  
- **Action Buttons:**  
  - “+ New Stash” to create new categories/goals.  
  - Quick links to badges or statistics screens.

### Statistics Screen  
- **Stash Summary List:** All stashes (save/spend) with progress bars.  
- **Filters/Toggles:** Switch between “All,” “In-Progress,” and “Completed.”  
- **Charts & Trends:** Compare monthly performance, show how many stashes are completed, and highlight cumulative ranking points.

### Achievements & Badges Screen  
- **Tabs/Sections:**  
  - “In-Progress” Stashes: Visual indicators of how close each stash is to completion.  
  - “Completed” Stashes: Earned badges for fully met monthly targets. Each completed stash corresponds to a badge.  
- **Ranking Display:** Show user’s overall rank or points.  
- **Badge Details Popup:** Explain how the stash was completed and reiterate the self-defined reward.

### Create/Edit Stash Popup  
- **Fields:** Name, Type (Save/Spend), Monthly Target, Reward Description, Notification Preferences.  
- **Save Button:** Updates the stash list and related statistics upon saving.

### Add Contribution/Expense Popup  
- **Fields:** Amount, Date, Optional Note.  
- **Progress Preview:** Show updated progress after contribution.

---

## Discussion on Self-Defined Rewards and Badges  
To avoid chaos in user-generated achievements, the system handles badges uniformly: completing a stash always yields a standard, system-defined badge. However, users can define a personal reward (e.g., “Treat yourself to a coffee”) that the system highlights when awarding the badge. This hybrid approach ensures a clean, consistent badge system while supporting personal motivation. The user-defined reward is a textual note rather than a full-blown badge design. This simplifies development and keeps the visual language consistent.

For ranking, each completed stash grants points. Points accumulate and advance the user’s rank. Pre-defined tiers (e.g., Bronze, Silver, Gold) provide a straightforward progression that’s easy to understand and encourages ongoing engagement.

---

# Wireframe Design Document

## Design Guidelines Reference  
Following Apple’s Human Interface Guidelines:  
- Use **points** as the measurement unit for iOS design. One point corresponds to one pixel on standard displays, and multiple pixels on high-density (“Retina”) displays. Typically, navigation bars are 44pt high, scaling accordingly on high-resolution screens.

## Common UI Elements

### Header Bar  
- Height: 44pt (standard)  
- Contains app title or screen title on the left, user profile or a simple settings icon on the right.  
- If adding segmented controls or tabs, consider an extended header bar (e.g., 64pt) to accommodate them without overcrowding.

### Footer Navigation  
- Standard 44pt tab bar with icons and labels for Home, Statistics, Badges, and Profile.  
- High-contrast icons and labels to ensure legibility.

### Typography & Color  
- Use Apple’s San Francisco typeface at recommended sizes (17pt for body text, 20pt+ for titles).  
- Maintain ample white space and a minimalist color palette, ensuring that accent colors (e.g., green for completed stashes) stand out.

## Screen Wireframe Overviews

### Home Screen (Wireframe)  
- **Header:** App name, Profile icon  
- **Main Content:**  
  - Monthly target overview (e.g., “You’ve completed 2/5 stashes this month!”)  
  - Scrollable list of in-progress stashes: progress bars, stash names, and quick-add buttons  
- **Footer:** Home, Statistics, Badges, Profile icons

### Statistics Screen (Wireframe)  
- **Header:** Title “Statistics”  
- **Main Content:**  
  - Filter buttons at top (All | In-Progress | Completed) in a segmented control  
  - List of stashes with completion percentages  
  - Charts at the bottom for monthly comparison
- **Footer:** Navigation bar

### Badges Screen (Wireframe)  
- **Header:** Title “Badges” + Rank Indicator  
- **Tabs/Sections:** In-Progress | Completed  
- **In-Progress Tab:** List of stashes nearing completion, small progress indicators  
- **Completed Tab:** Grid or list of earned badges, each linked to a completed stash  
- **Footer:** Navigation bar

### Create/Edit Stash Popup (Wireframe)  
- **Modal Layout:**  
  - Fields: Name (Text Field), Type (Save/Spend - Radio Buttons), Target (Number Field), Reward (Text Field), Notifications (Toggle)  
  - Save/Cancel Buttons

### Add Contribution Popup (Wireframe)  
- **Modal Layout:**  
  - Fields: Amount (Number Field), Date (Date Picker), Notes (Optional)  
  - Preview updated progress  
  - Save/Cancel Buttons

---

# Conclusion

This revised documentation accommodates the stakeholder’s updated requirements while preserving the minimalist ethos. It avoids daily targets, clarifies the “stash” concept, and makes user-defined rewards feasible without complicating the badge system. The ranking feature is integrated into a points-based progression. The wireframe guidelines and references to Apple’s Human Interface Guidelines ensure a solid starting point for the Figma design process.

Below is a revised version of the **Screen Layouts** and **Wireframe Design** sections, incorporating the requested changes. The use cases and initial description remain relevant, but the layout details now reintroduce the calendar, expand on the statistics functionality, and highlight the ranking mechanism more clearly. The minimalistic approach is maintained, but with richer data views and more meaningful navigation options.

---

# Revised Screen Layouts and Wireframe Design

## Key Revisions  
- **Calendar View Reintroduced:** A toggleable calendar integrated into the Home or a dedicated screen to show daily contributions/expenses. Users can see days marked with indicators if they have added any contribution or expense on that date.  
- **Comprehensive Statistics:** The Statistics screen now provides yearly/monthly/daily views, allowing for trend analysis. It includes more granular filters and charts.  
- **Ranking Mechanism Displayed:** Integrate a user rank or level indicator into either the Profile or Badges screen, showing how many points or completed stashes are needed to reach the next rank.

## Navigation Structure  
- **Tab Bar** (always visible on the bottom): Home | Statistics | Badges | Profile  
- **Header**: Contextual titles with optional filters or toggles.  
- **Pop-ups/Modals**: For creating/editing stashes and adding contributions/expenses.

---

## Screens Overview

### 1. Home Screen

**Purpose:** Quick snapshot of user’s overall monthly progress and easy access to daily contributions.

**Sections:**

- **Header Bar (44pt):**  
  - Left: App Logo or Name  
  - Right: User Profile Icon (tap navigates to Profile)

- **Monthly Overview Section:**  
  - Show total progress for the current month: "You’ve completed X out of Y stashes."  
  - A summary indicator: total saved and total spent for the month vs. monthly targets.

- **Calendar Toggle:**  
  - A button or segmented control to switch between a **List View** of stashes or a **Calendar View**.  
  - **Calendar View**:  
    - A compact monthly calendar grid or one-line/week view.  
    - Days with contributions or expenses have a small indicator (e.g., a green dot for savings, a red dot for spending).  
    - Tapping a day shows a tooltip or a small drawer listing that day’s transactions (amount saved or spent, notes, related stash).
  - **List View**:  
    - Shows the stashes in-progress with their progress bars and quick-add buttons.
  
- **Quick Actions:**  
  - “+ New Stash” button leading to the creation modal.  
  - “Add Entry” (if viewing a specific stash from a quick selection).

**Minimalism Note:** The Home screen remains clean with either a simple calendar plus minimal icons or a list of stashes. The user can toggle between these views for convenience.

---

### 2. Statistics Screen

**Purpose:** Provide in-depth insight into user’s financial behavior over different time frames (daily, monthly, yearly), across stashes, and overall performance.

**Layout Ideas:**

- **Header Bar (44pt):**  
  - Title: “Statistics”  
  - Right Side: A filter icon or segmented control.

- **Filters and Timeframe Toggles (just below Header):**  
  - Daily | Monthly | Yearly toggle (segmented control).  
  - Category Filter (All, Saving Stashes, Spending Stashes).  
  - Time-period picker (for selecting a specific month or year, if needed).

- **Key Metrics Display:**  
  - **Daily View:** Total contributions (saved), total expenses recorded that day, number of stashes updated. Possibly a small sparkline chart for the selected day’s position in the month.  
  - **Monthly View:** Bar or line chart showing total saved vs. total spent by day, top categories (which stash got the most savings or spending), and completion percentages for each stash.  
  - **Yearly View:** A heatmap or month-by-month overview (e.g., a bar chart summarizing each month’s total savings, spending, and number of completed stashes).
  
- **Stash Performance List:**  
  - Below the charts, list all stashes relevant to the filter/timeframe:  
    - Show their completion percentage, total amounts contributed or spent in that period, and how they compare to previous periods (e.g., “You saved 20% more than last month in your Vacation Fund.”).
  
- **Additional Insights:**  
  - Highlight completed stashes count for the selected period.  
  - Show total points earned from completed stashes in that timeframe, which contribute to user ranking.

**Minimalism Note:** Although richer, we keep charts and lists clean, use whitespace, and limit the number of colors to maintain a minimalistic, non-overwhelming design. The user can drill down by toggling filters rather than seeing all data at once.

---

### 3. Badges & Ranking Screen

**Purpose:** Display achievements, in-progress and completed stashes, and user’s rank.

**Sections:**

- **Header Bar (44pt):**  
  - Title: “Badges & Rank”

- **Ranking Display:**  
  - Prominent display of user’s current rank or level (e.g., “Level 3: Silver Saver”).  
  - A small progress bar or numerical indicator showing how many points until the next rank.

- **Tabs or Segmented Control:**  
  - In-Progress: Show stashes currently not completed this month, their progress, and any associated upcoming badges.  
  - Completed: Show badges for stashes fully achieved this month (or historically if you allow past badges). Each badge is a standardized icon with a description of what was achieved.  
  - (Optional) All-Time Achievements: If needed, a view that collects all past completions, ranks obtained, and total points accumulated over time.

- **Badge Details Modal:**  
  - Tapping a badge reveals its detail: associated stash name, completion date, the user-defined reward, and the points earned.

**Minimalism Note:** Keep the badges visually consistent, using a simple color palette. The rank system uses a straightforward point structure, not overly complicated graphics.

---

### 4. Create/Edit Stash Modal

**Fields:**
- Stash Name  
- Type: Save or Spend  
- Monthly Target  
- Optional: Long-Term Goal (if any) and user-defined reward text (e.g., “If I complete this stash, I get a…”)  
- Notification Preferences (on/off, frequency)  
- Save/Cancel

**Minimalism Note:** A simple vertical form with clear labels and a single primary action button (“Save”).

---

### 5. Add Contribution/Expense Modal

**Fields:**
- Amount (numeric keyboard)  
- Date (default: today, user can select another date)  
- Note (optional)  
- Save/Cancel

**After saving:**  
- Update stash progress immediately.  
- If the stash reaches completion criteria, trigger a “Receive Badge” notification or redirect user to Achievements.

**Minimalism Note:** Keep the input fields minimal and straightforward. A short success animation or a subtle confirmation message maintains a pleasant user experience without clutter.

---

### 6. Profile Screen

**Purpose:** Manage user account, preferences, and view cumulative rank info.

**Sections:**
- **Header Bar (44pt):** Title: “Profile”
  
- **User Info:** Username, Profile Picture  
- **Account Settings:** Language, Theme (light/dark), Notification Toggles  
- **Security & App Settings:** Password changes, logout  
- **Overall Achievements:** Summarize total stashes completed ever, total points earned, current rank. Link to the Badges & Ranking screen for detail.

**Minimalism Note:** Keep profile options neatly categorized with simple toggle switches and a clean layout.

---

## Wireframe Design Principles

- **Dimensions & Measurements:**  
  - Use points as the base unit for iOS design. Navigation bars at 44pt high. On Retina, these scale seamlessly.  
  - Keep spacing and padding consistent for a clean look.

- **Color & Typography:**  
  - Stick to a limited color palette (e.g., white background, dark text, a single accent color for progress bars and indicators).  
  - San Francisco font sizes: 17pt body, larger for headings (20-24pt).  
  - Icons and indicators should be simple shapes or Apple SF symbols for consistency.

- **Visual Hierarchy:**  
  - Statistics screen uses charts that are simple and clean—line charts or bar charts with limited labeling, focusing on essential info.  
  - Calendar dots are small but distinct.  
  - Use whitespace generously. Let the user focus on key data rather than overwhelming them with too much detail at once.

---

## Examples of Algorithms / Data Handling (Conceptual)

- **Ranking Algorithm:**  
  - Each completed stash earns a fixed number of points (e.g., 10 points).  
  - Accumulated points determine rank tiers. For example:  
    - 0-50 points = Bronze Rank  
    - 51-150 points = Silver Rank  
    - 151+ = Gold Rank  
  - This algorithm runs each time a stash completes to update the user’s rank.

- **Statistics Computations:**  
  - Daily totals: Sum all contributions/expenses logged on that day.  
  - Monthly totals: Aggregate daily amounts into monthly charts.  
  - Yearly view: Sum monthly totals into yearly data.  
  - Comparisons: Compare selected period’s totals to previous periods (store historical data each month).

- **Calendar Marking:**  
  - For each day with an entry, show a colored dot. Green for net positive savings, red if expenses exceed savings that day (if that’s applicable), or both colors if mixed entries.  
  - When the user taps a day, display a simple list of that day’s entries, amounts, and associated stash names.

---

# Conclusion

This revised version integrates the calendar for daily contribution visualization, provides richer statistics with daily/monthly/yearly views, and clarifies the ranking mechanism. Although the design remains minimalistic in style, the complexity and depth of available data, toggles, and filters allow users to gain deeper insights without feeling cluttered.