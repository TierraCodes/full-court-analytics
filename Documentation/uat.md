# User Acceptance Testing (UAT)

## Last Updated:
02/24/2026
---

# 1. Feature Overview

| Feature | Priority | Iteration | Client Facing (Y/N) |
|---------|----------|-----------|---------------------|
|Dashboard|High|1|Y|
|Coach Profile|High|1|Y|
|Email Management|Medium|3-5|Y|


---

# 2. Acceptance Scenarios

## Feature: Dashboard [Write down a more explanatory name for the feature]

### Scenario 1: Happy Path (Search Accuracy
**Given:**<br/>
The user is on the dashboard, and 'Ball State University' exists on the client's database<br/>
**When:**<br/>
The user types 'Ball' into the search bar. <br/>
**Then:**<br/>
The dashboard will display Ball State University immediately in the table.<br/>
**Status:** (Not Tested / Internal Passed / Client Accepted)<br/>
Internal Passed <br/>
**Evidence:** (link to PR, test file, video, screenshot) <br/>
https://github.com/eewmercer/full-court-analytics-code/blob/main/src/app/dashboard/__tests__/Dashboard.test.tsx <br/>
<img width="611" height="335" alt="Screenshot 2026-02-24 at 1 13 22 PM" src="https://github.com/user-attachments/assets/fdf545a1-e338-40ce-88c1-7bda7c49eb85" />
### Scenario 2: Error Handling
**Given:**
<br/>
**When:**
<br/>
**Then:**
<br/>
**Status:**
<br/>
**Evidence:**
<br/>
### Scenario 3: Edge Case
...

---

## Feature: Coach Profile [Write down a more explanatory name for the feature]

### Scenario 1: Happy Path (Clean UI and data accuracy)
**Given:** <br/>
The coach's profile is completed and exists in the database <br/>
**When:**<br/>
The user navigates to the coach's profile. <br/>
**Then:**<br/>
The profile will be present, easy to read, and show accurate data <br/>
**Status:** (Not Tested / Internal Passed / Client Accepted)<br/>
Client Accepted and internally checked <br/>
**Evidence:** (link to PR, test file, video, screenshot)<br/>
https://github.com/eewmercer/full-court-analytics-code/blob/main/src/app/coach/%5BcoachId%5D/__tests/CoachProfile.test.tsx <br/>
<img width="641" height="338" alt="image" src="https://github.com/user-attachments/assets/9252b760-8552-4cb6-88bd-7071ae18a8c4" />
<br/>
### Scenario 2: Error Handling
**Given:**

**When:**

**Then:**

**Status:**

**Evidence:**

### Scenario 3: Edge Case
...

---


## Feature: Emailing Coaches [Write down a more explanatory name for the feature]

### Scenario 1: Happy Path (Successful Transmission)
**Given:**<br/>
The user has composed an email to send to a coach via the program's interface.<br/>
**When:**<br/>
The user hits send.<br/>
**Then:**<br/>
The user's email is delivered to the recipient's inbox, and a 'Success' message is displayed to the user<br/>
**Status:** (Not Tested / Internal Passed / Client Accepted)<br/>
Client Accepted <br/>
**Evidence:** (link to PR, test file, video, screenshot)<br/>
We mock the email sending and make sure the data is correct and the "Email sent successfully" alert is shown<br/>
https://github.com/eewmercer/full-court-analytics-code/blob/main/src/app/coach/%5BcoachId%5D/__tests/CoachProfile.test.tsx <br/>
<img width="716" height="557" alt="image" src="https://github.com/user-attachments/assets/21c0b68c-5d49-46cb-8aa1-63debf564b51" />
<br/>
### Scenario 2: Error Handling
**Given:**

**When:**

**Then:**

**Status:**

**Evidence:**

### Scenario 3: Edge Case
...

---


## Feature: [Feature Name]

# 3. Client UAT Log

These tests are validated by the client.

| Date | Feature | Client Feedback | Action Required | Resolved (Y/N) |
|------|---------|-----------------|-----------------|----------------|
|3/16/2026|Dashboard Search Bar|Search bar correctly alters the dashboard results based on user input|N/A|Y|
|3/16/2026|Coach Profile UI Clarity and Appeal|UI looks good, looks just like the sketches on Figma|N/A|Y|
|3/16/2026|Sending Emails through Coach Profile|Given an account is already setup and has the Gmail token, he can send emails to the selected coach|Work on the robustness of the email sending|Should have time next iteration to finalise the refactor|

---

# 4. Open Acceptance Risks

## Risk1
- Risk:
- Mitigation Plan:

## Risk2
