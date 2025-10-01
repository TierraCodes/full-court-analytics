# Requirements
## Functional Requirements

* UC1:
  * FR1 (High): The system shall provide a search bar that accepts school name, location, or conference.
  * FR2 (Medium): The system shall display search suggestions as the user types (typeahead).
  * FR3 (High): The system shall provide filters to narrow down search results by division, conference, state, public/private, enrollment size, role type, date last updated, and user-generated tags.
  * FR4 (Medium): The system shall allow users to generate their own custom tags to organize the schools by.
  * FR5 (Low): The system shall provide recommended schools based on the user's location.

* UC2:
  * FR6 (High): The system shall display basic school information, including school name, location, division level, and conference.
  * FR7 (High): The system shall show the coaching staff with names, titles, photos, and contact information.
  * FR8 (Low): The system shall show available majors and academic programs at a school.
  * FR9 (Low): The system shall display academic support services available at a school.
  * FR10 (Medium): The system shall display statistics in both tabular and graphical formats.

* UC3:
  * FR11 (Medium): The system shall notify athletes when favored schools update their recruiting information.
  * FR12 (Medium): The system shall notify athletes when a favored school's contact information changes.
  * FR13 (High): The system shall log a history of communication with college staff.
  * FR14 (Medium): The system shall allow users to add notes to each logged staff interaction.
  * FR15 (High): The system shall display all logged communications with a specific school in chronological order.

* UC4:
  * FR16 (High): The system shall allow users to set reminders for follow-up communications.
  * FR17 (High): The system shall allow users to draft and send emails to college staff through email templates within the application.
  * FR18 (High): The system shall provide a "Contact Coach" button on each school profile page.
  * FR19 (Medium): The system shall allow users to select specific coaches or staff members to contact through the "Contact Coach" form.

* UC5:
  * FR18 (High): The system shall provide a table showing details of each staff member by name, role, email, phone, and last verified.
  * FR19 (Medium): The system shall allow users to add notes to specific schools.
  * FR20 (High): The system shall create staff profile pages detailing their contact info, role history, primary/secondary email, social links, last-contacted date, and do-not contact flags.

## Non-Functional Requirements
* UC1:
  * NFR1 (Medium): Filter operations shall update results in real-time.
  * NFR2 (Medium): The system shall display the number of results for each filter option before selection.
  * NFR3 (Medium): The system shall display the number of results based on their overall inquiry.
  * NFR4 (High): Users shall be able to clear all filters with a single "Reset" button.
 
* UC2:
  * NFR5 (High): School statistics shall be presented in an intuitive, easy-to-read format appropriate for high school students.
  * NFR6 (High): Font sizes shall be readable on desktop and mobile devices. Exact font-size up to the client's discretion.
  * NFR7 (Medium): Statistical charts and graphs shall load within 1 second of page-load.
  * NFR8 (Medium): If statistics are unavailable or fail to load, a clear message will be displayed rather than a blank space.

* UC3:
  * NFR9 (High): All logged communications will be saved automatically without requiring manual save actions.
  * NFR10 (High): Communication notes shall be private and viewable only by the athlete who created them.
  * NFR11 (Medium): The communication logging interface shall require no more than 3 clicks to create a new entry **(Up to client)**.

* UC4:
  * NFR12 (High): The contact interface shall be simple enough for first-time users to complete without instructions.
  * NFR13 (High): Email templates shall be customizable.
  * NFR14 (Low): The system shall provide real-time character count for messages to prevent overly long communications.
 
* UC5:
  * NFR15 (High): School overview pages shall follow a consistent layout across every school for easy comparison.
  * NFR16 (Medium): The system shall provide a table of contents or quick navigation for long profile pages.
  * NFR17 (High): All images shall include descriptive alt text for screen readers.
  * NFR18 (Medium): Missing or outdated information shall be clearly indicated to prompt updates.

 







