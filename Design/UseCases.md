# Actors

- **Athletes**  
  Main user group. Basketball players who search schools, log outreach, and track interest. They can also upload videos of gameplay, view schools in the dashboard, and track their stats in games.

- **Recruiting Advisors/Trainers**  
  Manage multiple players, provide structure and oversight. Trainers can identify target schools, share notes, and track coach engagement for the athletes they advise.

- **Parent/Guardian**  
  Support athletes in research, help manage notes and follow-ups, and provide consent if the athlete is underage.

---

# Use Cases – First Iteration

### UC1 – As an athlete, or advisor, I need to be able to view schools quickly within a filterable dashboard (BR1)
**Explanation:** Athletes and Advisors need to find schools quickly using accurate, verified data. This aligns with BR1 (Recruiting and Outreach Research). 

**Actors:** Athlete, Recruiting Advisors/Trainers 

**Flow:**  
1. Athlete enters a keyword (school name, location, or conference).  
2. System shows typeahead suggestions.  
3. Athlete applies basic filters (division, conference, state).  
4. Results list updates dynamically.  
5. Athlete selects a school to view its profile.  

---

### UC2 – As an athlete, or parent, I need to be able to view information on colleges and their data (BR1)
**Explanation:** Athletes need detailed information about schools in one place to evaluate recruiting opportunities. This aligns with BR1 (Recruiting and Outreach Research). 

**Actors:** Athlete, Parents/Guardian

**Flow:**  
1. Athlete selects a school from search results.  
2. System displays the school profile with:  
   - Overview (location, division, enrollment, conference)  
   - Staff table (coaches, contact info, last verified)  
3. Athlete reviews details and may favorite the school.  

---

### UC3 - As an athlete, I want to view general analytics to see my strengths and weaknesses (BR2)
**Explanation:** The primary goal of the analytics is to provide an athlete with a visual representation of what their strengths and weaknesses are, in statistical or graphical format, based on their previous performance in games. This supports BR2 (Analytical Aspect)

**Actors:** Athlete 

**Flow:**  
1. Athlete can view their player profile.
2. There are various tabs that they can view different statistics in: Overview, Game Log, Shot Types, Action Types, etc.
3. Each tab will provide either graphs, percentages, or data that applies to an athlete's personal performance.
Athlete can view the player profile page, and select the tabs related to specific plays
4. Knowing this specific play data will allow an athlete to view where they can improve performance on particular skills or moves.
---