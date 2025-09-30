# Actors
- Athletes: Main user, searches schools, logs outreach, tracks interest. Basketball players who can use the website to track their stats in games, upload videos of gameplay, or view schools in the dashboard.
  
- Recruiting Advisors/Trainers: Manages multiple players, provides structure and oversight. Trainers working with multiple athletes can identify target schools, share notes, and track coach engagement for the athletes they advise.
  
- Parent/Guardian: Supports player in research, helps manage notes and follow-ups. Users in charge of athletes; they provide consent required for the players if they are too young.
    
- System (Database/Search Engine): Provides search/filter functionality and returns results.
  
- Email/Notification Service: Sends reminders, updates, and outreach confirmations.

# Use Cases

### UC1 – Search & Filter Schools (BR1)
**Explanation:** Athletes need to find schools quickly using accurate, verified data. This supports the business requirement of centralizing recruiting research (BR1).  
**Actors:** Player, System.  
**Flow:**  
1. Player enters a keyword (school, coach, conference).  
2. System shows typeahead suggestions.  
3. Player applies filters (division, conference, location, enrollment size, role type, last updated).  
4. Results list updates dynamically.  
5. Player selects a school to view its profile.  

---

### UC2 – View School Profile (BR1)
**Explanation:** Athletes need detailed information about schools in one place to evaluate recruiting opportunities. This aligns with BR1.  
**Actors:** Athlete, System.  
**Flow:**  
1. Athlete selects a school from the search results or watchlist.  
2. System displays the school profile with:  
   - Overview (location, division, enrollment, conference).  
   - Staff table (coaches, contact info, last verified).  
   - Notes & intel (tags, interest level, custom notes).  
3. Player reviews details or navigates to coach profiles.  

---

### UC3 – Log Outreach with a Coach (BR2)
**Explanation:** Players need to record communications with coaches to track their recruiting journey and prevent missed opportunities. This supports BR2 (relationship & outreach management).  
**Actors:** Athlete, Coach Profile, Email/Notification Service.  
**Flow:**  
1. Player opens a coach profile.  
2. Player clicks “Log outreach.”  
3. Player chooses outreach type (email, call, note).  
4. System saves outreach record with timestamp.  
5. System updates the coach’s timeline and “last contacted” date.  

---

### UC4 – Schedule Follow-Up Reminder (BR2)
**Explanation:** Athletes must track follow-ups to strengthen coach relationships. This fulfills BR2.  
**Actors:** Athletes, Notification Service.  
**Flow:**  
1. Player opens a school or coach profile.  
2. Player selects “Schedule follow-up.”  
3. Player sets due date/time and optional recurrence.  
4. System stores the reminder and links it to the school/coach.  
5. Notification Service alerts player at the scheduled time.  

---

### UC5 – View Outreach Analytics Dashboard (BR2)
**Explanation:** Athletes and advisors need visibility into recruiting progress using outreach metrics. This supports BR2.  
**Actors:** Athlete, Advisor, System.  
**Flow:**  
1. Athlete/Advisor opens the Analytics Dashboard.  
2. System retrieves outreach and response data.  
3. Dashboard displays charts (touches by division/conference, response rates, timeline trends).  
4. Athlete/Advisor applies filters or drills into specific schools.  

 - *UC1*: View school statistics - BR2
    - This is an appropriate use case because the core of this website is to allow althletes to view school information and statistics. This use case is connected with BR2 because it fills the requirement of viewing a schools stats, figures, and allowing an athlete to be able to favorite schools.
- *UC2*: Log and take note of communication with staff - BR2
    -  (sample text)
- *UC5*: Get an in-depth overview of the school and staff - BR1
    -  (sample text)
- *UC6*: Get contact info and view social media links schools - BR2
    -  (sample text)
