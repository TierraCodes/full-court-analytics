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
* Nextjs API Routes
  * An API route allows clients to call APIs without needing to store security information client side.
  * This deserves a module as it will need to be accessed as a middleman to interact with the database.
* Backend
  * Our backend will serve as the middleman between the frontend and the API calls.
  * It will allow us to prepare data and create calls to the API to connect to the Db.
* Firebase functions/Cloud Run
  * Different types of API routes to interact with the Db in multiple ways.
  * This is important to have multiple different ways of interacting with the Db, rather than only having a URL type API.
* Firestore Db
  * The entire structure of the project revolves around the retrieval of data from the Firestore Database.
  * It deserves a module as the system would not work without any data to pull from.

---

## System Diagram (Mermaid)

```mermaid
graph TD
    A[User's Browser]
    B[Next.js/React Frontend]
    C{Firebase Authentication}
    D[Next.js API Routes]
    E[(Firestore Database)]
    F[Firebase functions]
    G[Backend Services]
    H[Google Cloud Run]
    

    A --> B 
    B -- Initial Load/Routing --> C
    C --> B
    B <-- Calls API (Read/Write) --> D
    B <-- Call API/Return data --> G
    G <--> H
    H <-- Connect to Db --> E
    G <--> F
    F <-- Connect to Db --> E
    D <--> E
    B --> A



