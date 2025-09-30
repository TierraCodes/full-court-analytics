# First Iteration Features

This document identifies the highest-priority functional requirements selected for the **first iteration** of the College Basketball Recruiting Database & Dashboard project. These requirements are drawn from the Requirements document and are directly connected to the Business Requirements (BR1: Centralized Recruiting Research, BR2: Outreach & Relationship Management).  

The goal of Iteration 1 is to deliver **functional software** that demonstrates the end-to-end flow: **Search → View → Save → Log**.  

---

## Selected Features

### 1. Display Basic School Information  
- **Requirement:** FR1 (High)  
- **Use Case:** UC1 – Search & View Schools  
- **Business Requirement:** BR1 – Centralized Recruiting Research  
- **Description:** The system shall display basic school information including school name, location, division level, and conference. This is the foundation of the project. Without accurate school info, users cannot make informed recruiting decisions.  

---

### 2. Display Coaching Staff on School Profiles  
- **Requirement:** FR2 (High)  
- **Use Case:** UC1 – View School Profile  
- **Business Requirement:** BR1 – Centralized Recruiting Research  
- **Description:** The system shall show coaching staff with names, titles, photos (if available), and contact information. Verified staff details are a core value proposition, making this an essential early feature.  

---

### 3. Search by School Name, Location, or Conference  
- **Requirement:** FR15 (High)  
- **Use Case:** UC4 – Search & Filter Schools  
- **Business Requirement:** BR1 – Centralized Recruiting Research  
- **Description:** The system shall provide a search bar that accepts school name, location, or conference. Enables users to quickly locate schools, forming the backbone of the recruiting research process.  

---

### 4. Typeahead Search Suggestions  
- **Requirement:** FR16 (High)  
- **Use Case:** UC4 – Search & Filter Schools  
- **Business Requirement:** BR1 – Centralized Recruiting Research  
- **Description:** The system shall display search suggestions as the user types. Improves usability and search efficiency, providing a modern user experience.  

---

### 5. Basic Filters for Search Results  
- **Requirement:** FR17 (High)  
- **Use Case:** UC4 – Search & Filter Schools  
- **Business Requirement:** BR1 – Centralized Recruiting Research  
- **Description:** The system shall provide filters to narrow down search results by division, conference, and state. Filtering makes large amounts of school data manageable and directly supports athletes in focusing their recruiting strategy.  

---

### 6. Log Outreach (Basic Note Entry)  
- **Requirement:** FR8 (High)  
- **Use Case:** UC2 – Log Outreach  
- **Business Requirement:** BR2 – Outreach & Relationship Management  
- **Description:** The system shall log a history of communication with college staff. In Iteration 1, this will be implemented as basic text notes. Even a simple log demonstrates relationship management and provides a baseline for more advanced outreach tracking later.  

---

### 7. Add Notes to Staff Interactions  
- **Requirement:** FR9 (High)  
- **Use Case:** UC2 – Log Outreach  
- **Business Requirement:** BR2 – Outreach & Relationship Management  
- **Description:** The system shall allow users to add notes to each logged staff interaction. Enhances the outreach log by letting users store context and personal details, critical for building relationships.  

---

## Stretch Goals (If Time Allows in Iteration 1)
- **FR5 (High):** Display school statistics in tabular form.  
- **FR18 (High):** Staff details table including email/phone/last verified date.  
- **FR19 (High):** Add notes to specific schools (not just staff).  

---

##  Expected Client Demo Flow
1. User **logs in** via Firebase Authentication.  
2. User **searches** for a school using the search bar + filters.  
3. User **views a school profile** with staff information.  
4. User **favorites** the school (watchlist stub).  
5. User **logs an outreach note** tied to that school.  

This flow demonstrates both **BR1 (Centralized Research)** and **BR2 (Outreach Management)** in action.  
