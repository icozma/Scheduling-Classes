# Scheduling-Classes

Repo support for [SSC - how-would-you-design-this-scheduling-classes](https://www.sqlservercentral.com/articles/how-would-you-design-this-scheduling-classes) exercise. 


```mermaid
erDiagram
    Student ||--o{ Course : Enrolls
    Student {
        int id PK
        int contactInformationId FK
        int userId FK
        string major
    }
    Course }o--|| ClassSchedule : Includes
    Course {
        int id PK
        string name
        string description
    }
    ClassSchedule }o--|| Instructor : TaughtBy
    ClassSchedule {
        int id PK
        int locationId FK
        int courseId FK
        int instructorId FK
        string name
        string description
        string time
    }
    
    Instructor ||--o{ Course : Teaches
    Instructor {
        int id PK
        int contactInformationId FK
        string department
    }

    ContactInformation }o--|| Instructor : Has
    ContactInformation }o--|| Student : Has
    ContactInformation {
        int id PK
        int userId FK
        string name
        string address
        string email
        string phone
    }

    Location }o--|| ClassSchedule : Has
    Location {
        int id PK
        string name
        string address
        string phone
    }

    Session }o--|| ClassSchedule : Has
    Session {
        int id PK
        int locationId  FK
        int courseId FK
        int instructorId FK
        string name
        string description
        string time
    }

    Volunteer }o--|| ClassSchedule : Has
    Volunteer {
        int id PK
        int contactInformationId
        int courseScheduleId
    }

    Review }o--|| Course : Has
    Review {
        int id PK
        int userId FK
        int courseId    FK
        int contactInformationId FK
        string name
        string description
        string rating
    }

    User }o--|| ContactInformation : Has

    User {
        int id PK
        int contactInformationId FK
        string userName
        string password
    }
    UserRegistration }o--|| User : Has
    UserRegistration {
        int id PK
        int userId FK
    }

    CourseRegistrations }o--|| ClassSchedule : Has
    CourseRegistrations {
        int id PK
        int userId FK
        int classScheduleId FK
    }

```
