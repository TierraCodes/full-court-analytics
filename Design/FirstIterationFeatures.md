# First Iteration Features

## Selected High-Priority Functional Requirements

The following requirements have been chosen from the Requirements document as the **highest-priority functional features** for Iteration 1. These directly support the updated Business Requirements (BR1 & BR2).  

### UC1 – Search & Filter Schools (Supports BR1)
- **FR1 (High):** The system shall provide a search bar that accepts school name, location, or conference.  
- **FR2 (Medium):** The system shall display search suggestions as the user types (typeahead).  
- **FR3 (High):** The system shall provide filters to narrow down search results by division, conference, state, public/private, enrollment size, role type, date last updated, and user-generated tags.  

### UC2 – View School Profile (Supports BR1)
- **FR6 (High):** The system shall display basic school information, including school name, location, division level, and conference.  
- **FR7 (High):** The system shall show the coaching staff with names, titles, photos, and contact information.  
- **FR10 (Medium):** The system shall display statistics in both tabular and graphical formats.  

### UC3 – View Player Analytics (Supports BR2)
- **FR13 (High):** The system shall allow users to view shot types from game data.  
- **FR14 (High):** The system shall allow users to view action types from game data.  
- **FR15 (High):** The system shall provide distinct tabs showcasing specific player stats.  

---

## Iteration 1 Functional Flow
1. Athlete enters a **school name** in the search bar.  
2. System provides **typeahead suggestions** and allows filters to be applied.  
3. Athlete selects a school from results.  
4. The **School Profile Page** displays:  
   - Basic school info (name, location, division, conference).  
   - Coaching staff details (names, titles, photos, contact info).  
   - Basic statistics in table/graph format.  
5. Athlete navigates to their **Player Analytics tab**, where they can view:  
   - Shot types from game data.  
   - Action types from game data.  
   - Tabs showing player-specific statistics.  

---

## GitHub Project Setup

Each requirement will be created as a **card in the project board** with columns: **To Do | In Progress | Done**.

- [ ] FR1 – Search bar (school name, location, conference)  
- [ ] FR2 – Typeahead search suggestions  
- [ ] FR3 – Filters for narrowing search  
- [ ] FR6 – Display school information  
- [ ] FR7 – Display coaching staff  
- [ ] FR10 – Display statistics  
- [ ] FR13 – Display shot types  
- [ ] FR14 – Display action types  
- [ ] FR15 – Player stats tabs  

---

## Justification

- These features represent the **core business requirements**:  
  - **BR1** – Centralized recruiting: athletes can search schools, view staff, and analyze stats.
