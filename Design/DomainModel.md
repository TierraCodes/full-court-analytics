# Domain Model

Used Mermaid Live to create a domain model based on project requirements, following UML Class Diagram.

---

## UML Class Diagram

```mermaid
classDiagram
direction TB
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

    class Player {
	    +boolean subscriptionStatus
    }

    class ParentGuardian {
	    +userID linkedChildID
    }

    class RecruitingAdvisor {
	    +userID linkedPlayerID
	    +int athleteCount
    }

    class School {
	    +id schoolID
		+id divisionID
		+int entrollmentCost
	    +String name
	    +String division
	    +String conference
	    +String state
	    +String publicPrivate
		+String website
		+List notes
	    +Map socialLinks
    }

    class Coach {
	    +id coachID
	    +String name
	    +String role
	    +String email
	    +String phone
	    +Date lastVerified
		+List roleHistory
	    +Map socialLinks
    }

    class Conference {
	    +id conferenceID
	    +List divisionID
	    +String location
    }

    class Note {
	    +id noteID
	    +String noteContent
	    +Date noteCreated
    }

    class OutreachLog {
	    +id outreachID
	    +String status
	    +String interestLevel
		+Date coachLastContactDate
    }

    class Tag {
	    +id tagID
	    +List listSchoolID
	    +String label
		+boolean doNotContactSchool
    }

    class CommunicationManagement {
	    -id userID
	    -Date date
	    -String content
	    -String type
    }

	class Analytics {
		+id playerID
		+id gameID
		+id possesionID
	}

	class Game {
		+id gameID
		+Map gameLog
		+Map shotCharts
		+addGameLog()
		+addShotChart()
	}

	class Possesion {
		+id possesionID
		+String actionType
		+String shotType
		+Map shooting
		+Map shotQuality
		+addShotType()
	}

	class Season {
		+int year
		+gameRange()
	}

	<<Abstract>> CommunicationManagement
	<<Abstract>> Analytics

	note for User "Target audience for who will be using this app. Different target users, each having same fundamental attributes and functions for outreach/orginization."
	note for Player "Athlete actively pursuing recruitment. They are primary subscribes, having a specific ID which can be referenced to ParentGuardian/RecruitingAdvisor users."
	note for ParentGuardian "Parent/guardian linked to player by playerID. Help review recruiting outreach for support."
	note for RecruitingAdvisor "Advisor working with multiple athletes, refrencing playerID. Use database to track schools and outreach for each athlete."
	note for School "Represents college basketball program within recruiting database. Holds key identifying info that users can filter/serach for and communicate with."
	note for Coach "Individual staff member linked to school. Provides key contact info used for ourtreach in recruiting process."
	note for Conference "More specific grouping of schools with division. Organized regionally/competitively."
	note for Note "Custom text added by user to track insights about school/coach tracking important details."
	note for OutreachLog "Record of communication between user and school/coach (calls, emails, etc.). Tracks date, type, and status for follow-ups and interest level."
	note for Tag "Custom label applied by user to help filter and orgainze by preference."
	note for CommunicationManagement "General bucket for all ways a player can interact/keep track with schools."
	note for Analytics "Represents athlete analytics during a specific game within a season."
	note for Game "Track court shots, game log, and player's possesion within game."
	note for Possesion "Player possesion shot types, quality, actions."
	note for Season "Game season."

    User <|-- Player
    User <|-- ParentGuardian
    User <|-- RecruitingAdvisor
    User "1" --> "*" CommunicationManagement
	User "1" --> "*" Analytics
    User "1" --> "*" Tag

    School "1" --> "*" Coach
    School "1" --> "1" Conference

    CommunicationManagement <|-- Note
    CommunicationManagement <|-- OutreachLog

	Analytics <-- Game
	Analytics <-- Possesion
	Analytics <-- Season
