# First Iteration Features

## Selected High-Priority Functional Requirements

The following requirements have been chosen from the Requirements document as the **highest-priority functional features** for Iteration 1. These will provide the minimum functional loop (search → view school info → see staff and stats) and will demonstrate a working system to the client.

### UC1 – Search & Filter Schools
- **FR1 (High):** The system shall provide a search bar that accepts school name, location, or conference.  
- **FR2 (Medium):** The system shall display search suggestions as the user types (typeahead).  
- **FR3 (High):** The system shall provide filters to narrow down search results by division, conference, state, public/private, enrollment size, role type, date last updated, and user-generated tags.  

### UC2 – View School Profile
- **FR6 (High):** The system shall display basic school information, including school name, location, division level, and conference.  
- **FR7 (High):** The system shall show the coaching staff with names, titles, photos, and contact information.  
- **FR10 (Medium):** The system shall display statistics in both tabular and graphical formats.  

---

## Iteration 1 Functional Flow
1. Athlete enters a **school name** in the search bar.  
2. System provides **typeahead suggestions** and allows filters to be applied.  
3. Athlete selects a school from results.  
4. The **School Profile Page** displays:  
   - Basic school info (name, location, division, conference).  
   - Coaching staff details (names, titles, photos, contact info).  
   - Basic statistics in table/graph format.  

---

## GitHub Project Setup

Each requirement will be created as a **card in the project board** with columns: **To Do | In Progress | Done**.

- [ ] FR1 – Search bar (school name, location, conference)  
- [ ] FR2 – Typeahead search suggestions  
- [ ] FR3 – Filters for narrowing search  
- [ ] FR6 – Display school information  
- [ ] FR7 – Display coaching staff  
- [ ] FR10 – Display statistics  

---

## Justification

- These features represent the **core business requirements**:  
  - **BR1** – Centralized school search and evaluation.  
  - **BR2** – Foundation for outreach and relationship management.  
- They are **functional**: the system will be able to search, display schools, and present staff + stats in a usable interface.  
- They can be achieved with the current **Next.js frontend + Firebase backend architecture**, making them realistic for the first iteration.  

---
