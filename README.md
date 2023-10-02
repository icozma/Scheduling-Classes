# Scheduling-Classes

Repo support for [SSC - how-would-you-design-this-scheduling-classes](https://www.sqlservercentral.com/articles/how-would-you-design-this-scheduling-classes) exercise.




```mermaid
erDiagram
    Student ||--o{ Course : Enrolls
    Student {
        string id
        string contactInformationId
        string major
    }
    Course }o--|| ClassSchedule : Includes
    Course {
        string id
        string name
        string description
    }
    ClassSchedule }o--|| Instructor : TaughtBy
    ClassSchedule {
        string id
        string name
        string description
        string time
        string locationId
        string courseId
        string instructorId
    }
    
    Instructor ||--o{ Course : Teaches
    Instructor {
        string id
        string contactInformationId
        string department
    }

    ContactInformation }o--|| Instructor : Has
    ContactInformation }o--|| Student : Has
    ContactInformation {
        string id
        string name
        string address
        string email
        string phone
    }

    Location }o--|| ClassSchedule : Has
    Location {
        string id
        string name
        string address
        string phone
    }

    Session }o--|| ClassSchedule : Has
    Session {
        string id
        string name
        string description
        string time
        string locationId
        string courseId
        string instructorId
    }

    Volunteer }o--|| ClassSchedule : Has
    Volunteer {
        string id
        string contactInformationId
        string courseScheduleId
    }

    Review }o--|| Course : Has
    Review {
        string id
        string name
        string description
        string rating
        string courseId
        string conttactInformationId
    }

```
