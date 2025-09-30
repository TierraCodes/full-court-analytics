# Actors

- **Athletes**  
  Main user group. Basketball players who search schools, log outreach, and track interest. They can also upload videos of gameplay, view schools in the dashboard, and track their stats in games.

- **Recruiting Advisors/Trainers**  
  Manage multiple players, provide structure and oversight. Trainers can identify target schools, share notes, and track coach engagement for the athletes they advise.

- **Parent/Guardian**  
  Support athletes in research, help manage notes and follow-ups, and provide consent if the athlete is underage.

- **System (Database/Search Engine)**  
  Provides search and filter functionality and returns results.

- **Email/Notification Service**  
  Sends reminders, updates, and outreach confirmations (future iterations).

---

# Use Cases – First Iteration

### UC1 – Search & Filter Schools (BR1)
**Explanation:** Athletes need to find schools quickly using accurate, verified data. This supports the business requirement of centralizing recruiting research (BR1).  
**Actors:** Athlete, System  
**Flow:**  
1. Athlete enters a keyword (school name, location, or conference).  
2. System shows typeahead suggestions.  
3. Athlete applies basic filters (division, conference, state).  
4. Results list updates dynamically.  
5. Athlete selects a school to view its profile.  

---

### UC2 – View School Profile (BR1)
**Explanation:** Athletes need detailed information about schools in one place to evaluate recruiting opportunities. This aligns with BR1.  
**Actors:** Athlete, System  
**Flow:**  
1. Athlete selects a school from search results.  
2. System displays the school profile with:  
   - Overview (location, division, enrollment, conference)  
   - Staff table (coaches, contact info, last verified)  
3. Athlete reviews details and may favorite the school.  

---

### UC3 – Log Outreach with a Coach (Basic Note Entry) (BR2)
**Explanation:** Athletes need to record communications with coaches to track their recruiting journey and prevent missed opportunities. This supports BR2 (relationship & outreach management).  
**Actors:** Athlete, System  
**Flow:**  
1. Athlete opens a school or coach profile.  
2. Athlete clicks “Log outreach.”  
3. Athlete enters a text note describing the communication.  
4. System saves the outreach note with a timestamp.  
5. Note is displayed in the communication history for that school/coach.  

---

# Use Cases – Deferred to Future Iterations

- **UC4 – Schedule Follow-Up Reminder (BR2)**  
  Will be implemented once notification service is integrated.  

- **UC5 – View Outreach Analytics Dashboard (BR2)**  
  Will be implemented once outreach data and reporting features are in place.  

- **UC6 – Extended School & Staff Data (BR1)**  
  Displaying stats, majors, academic services, and additional metadata about schools.  

- **UC7 – Contact Coach Directly (BR2)**  
  Contact buttons and preloaded templates for outreach.  
