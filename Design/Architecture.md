# Architecture

* User Browser/ Mobile App:
  * The user browser serves as the host for the UI to be displayed and allows for user data entry and triggering of API calls.
  * It is a module as the user browser allows interaction with the system and database as a whole.
* Next.js/React Frontend
  * The frontend prepares the data and UI for the user to interact with.
  * It is a module as the frontend organizes the necessary data in a visually appealing way. It serves as a foundation for user interactivity.
* Firebase Authentication
  * The addition of an authentication system allows for secure access of the application by the users.
  * It is worthy of a module as it consistently interacts with the system to authenticate users.
* Backend API/Nextjs API Routes
  * An API route allows clients to call APIs without needing to store security information client side.
  * This deserves a module as it will need to be accessed as a middleman to interact with the database.
* Firestore Db
  * The entire structure of the project revolves around the retrieval of data from the Firestore Database.
  * It deserves a module as the system would not work without any data to pull from.
* External Recruiter Firestore Db
  * This changes the architecture as we will now need to access an external API endpoint.
  * This database will be accessed frequently to retrieve misc information about schools and staff members.

---

## System Diagram (Mermaid)

```mermaid
graph TD
    A[User's Browser / Mobile App]
    B[Next.js/React Frontend]
    C{Firebase Authentication}
    D[Backend API/Next.js API Routes]
    E[(Firestore Database)]
    F[(Recruiter Firestore Database)]

    A --> B 
    B -- Initial Load/Routing --> C
    C --> B
    B -- Calls API (Read/Write) --> D
    D -- Gets External Data from Recruiter Database --> F
    D --> E
    B --> A



