# User Acceptance Testing (UAT)

## Last Updated:
04/13/2026
---

# 1. Feature Overview

| Feature | Priority | Iteration | Client Facing (Y/N) |
|---------|----------|-----------|---------------------|
|Dashboard|High|1|Y|
|Coach Profile|High|1|Y|
|School Profile|High|2|Y|
|Tags / Custom Tag Management|Medium|2-3|Y|
|Email Management Page|Medium|4|Y|
|Email Sending via Gmail|High|3-4|Y|
|User Notes|Medium|1-2|Y|
|User Profile|Low|1-2|Y|
|Favorites (Schools & Coaches)|Medium|1-2|Y|
|Bulk Email / Bulk Actions|Medium|4-5|Y|
|Email Templates|Medium|3-4|Y|
|Login / Registration|High|1|Y|

---

# 2. Acceptance Scenarios

## Feature: Dashboard (Search and Filtering)

### Scenario 1: Happy Path (Search Accuracy)
**Given:**<br/>
The user is on the dashboard, and 'Ball State University' exists on the client's database<br/>
**When:**<br/>
The user types 'Ball' into the search bar.<br/>
**Then:**<br/>
The dashboard will display Ball State University immediately in the table.<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/dashboard.cy.ts` – UAT 1.1<br/>

### Scenario 2: Error Handling (No Results Found)
**Given:**<br/>
The user is on the dashboard<br/>
**When:**<br/>
The user types a school name that does not exist in the database (e.g., "zzzzz")<br/>
**Then:**<br/>
The table shows zero results and does not crash or display stale data<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/dashboard.cy.ts` – UAT 1.2<br/>

### Scenario 3: Edge Case (Filter Combination)
**Given:**<br/>
The user is on the dashboard<br/>
**When:**<br/>
The user applies multiple filters simultaneously (e.g., Division I, a specific state, and a custom tag)<br/>
**Then:**<br/>
The table updates to show only results matching all active filters, and pagination resets to page 1<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/dashboard.cy.ts` – UAT 1.3<br/>

---

## Feature: Coach Profile (Data Accuracy and Interaction)

### Scenario 1: Happy Path (Clean UI and Data Accuracy)
**Given:**<br/>
The coach's profile is complete and exists in the database<br/>
**When:**<br/>
The user navigates to the coach's profile.<br/>
**Then:**<br/>
The profile is present, easy to read, and shows accurate data including name, school, phone, socials, email history, notes, and tags<br/>
**Status:**<br/>
Client Accepted and internally checked<br/>
**Evidence:**<br/>
`cypress/e2e/coachProfile.cy.ts` – UAT 2.1<br/>

### Scenario 2: Error Handling (Coach Not Found)
**Given:**<br/>
The user navigates to a coach profile URL with an invalid or nonexistent coach ID<br/>
**When:**<br/>
The page attempts to load coach data from the database<br/>
**Then:**<br/>
The page displays a meaningful error or empty state rather than crashing<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/coachProfile.cy.ts` – UAT 2.2<br/>

### Scenario 3: Edge Case (Incomplete Coach Data)
**Given:**<br/>
A coach record exists but is missing optional fields (e.g., phone number, socials)<br/>
**When:**<br/>
The user navigates to that coach's profile<br/>
**Then:**<br/>
The profile renders without errors; missing fields are either hidden or shown as a placeholder<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/coachProfile.cy.ts` – UAT 2.3<br/>

---

## Feature: School Profile (Data and Coaches Roster)

### Scenario 1: Happy Path (School Data and Coach List)
**Given:**<br/>
A school record exists in the database with associated coaches<br/>
**When:**<br/>
The user navigates to the school's profile page<br/>
**Then:**<br/>
The school's name, conference, division, and phone number are displayed, along with a list of associated coaches that are individually linkable<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/schoolProfile.cy.ts` – UAT 3.1<br/>

### Scenario 2: Error Handling (School Not Found)
**Given:**<br/>
The user navigates to a school profile URL with an invalid or nonexistent school ID<br/>
**When:**<br/>
The page attempts to fetch the school record from the database<br/>
**Then:**<br/>
The page displays a meaningful error or empty state and does not crash<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/schoolProfile.cy.ts` – UAT 3.2<br/>

### Scenario 3: Edge Case (School With No Coaches)
**Given:**<br/>
A valid school record exists but has no associated coach records<br/>
**When:**<br/>
The user navigates to that school's profile<br/>
**Then:**<br/>
The profile loads successfully and the coach list displays an empty state rather than an error<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/schoolProfile.cy.ts` – UAT 3.3<br/>

---

## Feature: Tags / Custom Tag Management (Create, Rename, Delete, Apply)

### Scenario 1: Happy Path (Create and Apply a Tag)
**Given:**<br/>
The user is logged in and on the Tags management page<br/>
**When:**<br/>
The user creates a new school or coach tag with a unique name and then applies it to a coach or school from that entity's profile<br/>
**Then:**<br/>
The tag appears in the tag list and is visibly applied to the selected entity in the dashboard and on the profile<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/tags.cy.ts` – UAT 4.1<br/>

### Scenario 2: Error Handling (Duplicate Tag Name)
**Given:**<br/>
The user already has a tag named "Target"<br/>
**When:**<br/>
The user attempts to create a second tag also named "Target" of the same type<br/>
**Then:**<br/>
The system prevents the creation and displays an appropriate error message<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/tags.cy.ts` – UAT 4.2 (empty name blocked; Add Tag button remains disabled)<br/>

### Scenario 3: Edge Case (Delete a Tag in Use)
**Given:**<br/>
A tag is currently applied to one or more coaches or schools<br/>
**When:**<br/>
The user deletes that tag from the Tags page<br/>
**Then:**<br/>
The tag is removed from the tag list and is no longer displayed on any previously tagged entity<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/tags.cy.ts` – UAT 4.3 (rename then delete flow)<br/>

---

## Feature: Email Management Page (Inbox, Sent, Drafts, Templates)

### Scenario 1: Happy Path (View Sent Emails and Replies)
**Given:**<br/>
The user has previously sent emails through the application and their Gmail account is connected<br/>
**When:**<br/>
The user navigates to the Email Management page and selects the Sent tab<br/>
**Then:**<br/>
Previously sent emails are listed with subject, recipient, and date; the user can expand an email to view replies in the thread<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/emailManagement.cy.ts` – UAT 5.1<br/>

### Scenario 2: Error Handling (Gmail Sync Failure)
**Given:**<br/>
The user's Gmail OAuth token has expired or been revoked<br/>
**When:**<br/>
The user attempts to sync or view the inbox/replies on the Email Management page<br/>
**Then:**<br/>
A clear error message is displayed prompting the user to re-authenticate with Gmail; the rest of the page remains functional<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/emailManagement.cy.ts` – UAT 5.2<br/>

### Scenario 3: Edge Case (Save and Load a Draft)
**Given:**<br/>
The user has started composing an email and saved it as a draft<br/>
**When:**<br/>
The user opens the Drafts section and selects the saved draft<br/>
**Then:**<br/>
The compose modal opens pre-populated with the draft's subject, body, and recipient<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/emailSending.cy.ts` – UAT 6.3<br/>

---

## Feature: Email Sending via Gmail (Successful Transmission)

### Scenario 1: Happy Path (Successful Send)
**Given:**<br/>
The user has composed an email to send to a coach via the program's interface and their Gmail account is authenticated<br/>
**When:**<br/>
The user clicks Send<br/>
**Then:**<br/>
The email is delivered to the recipient's inbox, a 'Email sent successfully' message is displayed, and the email is recorded in the sent history on the coach's profile<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
We mock the email sending and make sure the data is correct and the "Email sent successfully" alert is shown<br/>
`cypress/e2e/emailSending.cy.ts` – UAT 6.1 (end-to-end via Mailhog SMTP)<br/>

### Scenario 2: Error Handling (Gmail Not Authorized)
**Given:**<br/>
The user has not connected their Gmail account or the OAuth token is missing<br/>
**When:**<br/>
The user attempts to send an email<br/>
**Then:**<br/>
An authentication dialog is displayed prompting the user to connect their Gmail account; no email is sent and no error is silently swallowed<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/emailSending.cy.ts` – UAT 6.2 (401 intercepted, auth dialog asserted)<br/>

### Scenario 3: Edge Case (Bulk Email to Multiple Recipients)
**Given:**<br/>
The user has selected multiple coaches or a school's coaching staff in the dashboard or school profile<br/>
**When:**<br/>
The user initiates a bulk email via the Bulk Actions dropdown and sends the composed message<br/>
**Then:**<br/>
Each selected recipient receives the email, personalization variables (if used) are resolved correctly per recipient, and a success or partial-failure summary is shown<br/>
**Status:**<br/>
Not Tested<br/>
**Evidence:**<br/>

---

## Feature: User Notes (Private Notes on Coaches and Schools)

### Scenario 1: Happy Path (Create and Save a Note)
**Given:**<br/>
The user is viewing a coach or school profile<br/>
**When:**<br/>
The user clicks the edit icon on the Notes card, types a note, and clicks Save<br/>
**Then:**<br/>
The note is persisted to the database, the card exits edit mode, and the saved text is displayed on the profile<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/userNotes.cy.ts` – UAT 7.1<br/>

### Scenario 2: Error Handling (Save Failure)
**Given:**<br/>
The user has typed a note and clicked Save, but a network or database error occurs during the save<br/>
**When:**<br/>
The save request fails<br/>
**Then:**<br/>
An "Error saving note." message is displayed; the note text is preserved in the editor so the user does not lose their work<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/userNotes.cy.ts` – UAT 7.2 (cancel discards and shows status message)<br/>

### Scenario 3: Edge Case (Cancel Discards Changes)
**Given:**<br/>
The user has opened the Notes card in edit mode and modified the existing note<br/>
**When:**<br/>
The user clicks Cancel or clicks outside the card<br/>
**Then:**<br/>
The note reverts to its pre-edit value and no changes are persisted<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/userNotes.cy.ts` – UAT 7.3 (Escape key cancels edit)<br/>

---

## Feature: User Profile (Bio, Personal Info, Email History)

### Scenario 1: Happy Path (Edit and Save Bio)
**Given:**<br/>
The user is on their User Profile page<br/>
**When:**<br/>
The user edits their bio and saves<br/>
**Then:**<br/>
The updated bio is reflected immediately on the profile page and persisted to the database<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/userProfile.cy.ts` – UAT 8.1<br/>

### Scenario 2: Error Handling (Profile Update Failure)
**Given:**<br/>
The user attempts to save profile changes but a database write error occurs<br/>
**When:**<br/>
The save request fails<br/>
**Then:**<br/>
An error message is displayed; the profile reverts to the last saved state<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/userProfile.cy.ts` – UAT 8.2<br/>

---

## Feature: Favorites (Star Schools and Coaches)

### Scenario 1: Happy Path (Favorite a School)
**Given:**<br/>
The user is on the dashboard or a school/coach profile<br/>
**When:**<br/>
The user clicks the star icon next to a school or coach<br/>
**Then:**<br/>
The star fills in, the entity is added to the user's favorites list, and the "Show Favorites Only" toggle on the dashboard surfaces it<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/favorites.cy.ts` – UAT 9.1<br/>

### Scenario 2: Error Handling (Favorite Toggle Failure)
**Given:**<br/>
The user clicks the star icon but a database error occurs<br/>
**When:**<br/>
The favorite/unfavorite request fails<br/>
**Then:**<br/>
The star icon reverts to its previous state and an error indicator is shown<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/favorites.cy.ts` – UAT 9.2 (unfavoriting in favorites-only view removes entry)<br/>

### Scenario 3: Edge Case (Favorite from School Profile)
**Given:**<br/>
The user is on a school's profile page<br/>
**When:**<br/>
The user clicks the star button on the profile<br/>
**Then:**<br/>
The star toggles to filled/active and the school appears when the Favorites Only filter is enabled on the dashboard<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/favorites.cy.ts` – UAT 9.3<br/>

---

## Feature: Login / Registration (Authentication)

### Scenario 1: Happy Path (Successful Login)
**Given:**<br/>
A registered user exists in the Firebase Auth system<br/>
**When:**<br/>
The user enters valid credentials and clicks Log In<br/>
**Then:**<br/>
The user is authenticated, redirected to the dashboard, and the header and sidebar reflect the logged-in state<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/login.cy.ts` – UAT 12.1<br/>

### Scenario 2: Error Handling (Invalid Credentials)
**Given:**<br/>
The user enters an incorrect email or password on the login page<br/>
**When:**<br/>
The user clicks Log In<br/>
**Then:**<br/>
A descriptive Firebase error message is displayed; the user remains on the login page<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/login.cy.ts` – UAT 12.2<br/>

### Scenario 3: Edge Case (Protected Route Redirect)
**Given:**<br/>
The user is not logged in<br/>
**When:**<br/>
The user attempts to visit a protected route directly (e.g., `/dashboard`)<br/>
**Then:**<br/>
The user is redirected to the login page<br/>
**Status:**<br/>
Internal Passed<br/>
**Evidence:**<br/>
`cypress/e2e/login.cy.ts` – UAT 12.3<br/>

---

# 3. Client UAT Log

These tests are validated by the client.

| Date | Feature | Client Feedback | Action Required | Resolved (Y/N) |
|------|---------|-----------------|-----------------|----------------|
|3/16/2026|Dashboard Search Bar|Search bar correctly alters the dashboard results based on user input|N/A|Y|
|3/16/2026|Coach Profile UI Clarity and Appeal|UI looks good, looks just like the sketches on Figma|N/A|Y|
|3/16/2026|Sending Emails through Coach Profile|Given an account is already setup and has the Gmail token, he can send emails to the selected coach|Work on the robustness of the email sending|Should have time next iteration to finalise the refactor|

---

# 4. Open Acceptance Risks
