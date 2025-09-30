# Domain Model

Used Mermaid Live to create a domain model based on project requirements, following UML Class Diagram.

---

## UML Class Diagram

```mermaid
classDiagram
    class User {
        +id userID
        +String name
        +String email
        +String role
        +login()
        +outreach()
        +makeTag()
        +makeNote()
    }

    note for User "Target audience for who will be using this app. Different target users, each having same fundamental attributes and functions for outreach/orginization."

    class Player {
        +boolean subscriptionStatus
    }

    note for Player "Athlete actively pursuing recruitment. They are primary subscribes, having a specific ID which can be referenced to ParentGuardian/RecruitingAdvisor users."

    class ParentGuardian {
        +userID linkedChildID
    }

    note for ParentGuardian "Parent/guardian linked to player by playerID. Help review recruiting outreach for support."

    class RecruitingAdvisor {
        +userID linkedPlayerID
        +int athleteCount
    }

    note for RecruitingAdvisor "Advisor working with multiple athletes, refrencing playerID. Use database to track schools and outreach for each athlete."

    class School {
        +id schoolID
        +String name
        +String division
        +String conference
        +String state
        +String publicPrivate
        +int entrollmentCost
    }

    note for School "Represents college basketball program within recruiting database. Holds key identifying info that users can filter/serach for and communicate with."

    class Coach {
        +id coachID
        +String name
        +String role
        +String email
        +String phone
        +Date lastVerified
    }

    note for Coach "Individual staff member linked to school. Provides key contact info used for ourtreach in recruiting process."

    class CoachProfile {
        +List roleHistory
        +Map socialLinks
        +Date lastContacted
        +boolean doNotContact
    }

    note for CoachProfile "Extended details about coach, like role history, socials, and last-contacted data. Helps athletes and advisors understand relationship history."

    class Conference {
        +id conferenceID
        +List divisionID
        +String location
    }

    note for Conference "More specific grouping of schools with division. Organized regionally/competitively."

    class Division {
        +id divisionID
    }

    note for Division "Competitive levle of school, and a broad way for players to filter."

    class SchoolProfile {
        +String website
        +List socialLinks
        +List notes
    }

    note for SchoolProfile "Extended info about school, including website, socials, and unique notes. Helps players understand proram's culture and preferences."

    class Note {
        +id noteID
        +String noteContent
        +Date noteCreated
    }

    note for Note "Custom text added by user to track insights about school/coach tracking important details."

    class OutreachLog {
        +id outreachID
        +String status
        +String interestLevel
    }

    note for OutreachLog "Record of communication between user and school/coach (calls, emails, etc.). Tracks date, type, and status for follow-ups and interest level."

    class Tag {
        +id tagID
        +List listSchoolID
        +String label
    }

    note for Tag "Custom label applied by user to help filter and orgainze by preference."

    class Notification {
        +id notificationID
        +String message
    }

    note for Notification "Reminders/updates delivered to users (staff changes, follow-ups, etc.). "

    class CommunicationManagement
    <<Abstract>> CommunicationManagement
    class CommunicationManagement {
        -id userID
        -Date date
        -String content
        -String type
    }

    note for CommunicationManagement "General bucket for all ways a player can interact/keep track with schools."

    User <|-- Player
    User <|-- ParentGuardian
    User <|-- RecruitingAdvisor
    User "1" --> "*" CommunicationManagement
    User "1" --> "*" Tag
    School "1" --> "*" Coach
    School "1" --> "1" Conference
    School --> SchoolProfile
    Coach --> CoachProfile
    Conference --> Division
    CommunicationManagement <|-- Note
    CommunicationManagement <|-- OutreachLog
    CommunicationManagement <|-- Notification
