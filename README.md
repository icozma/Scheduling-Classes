# Scheduling-Classes

Repo support for [SSC - how-would-you-design-this-scheduling-classes](https://www.sqlservercentral.com/articles/how-would-you-design-this-scheduling-classes) exercise.




```mermaid
erDiagram
    Student ||--o{ Course : Enrolls
    Student {
        int id
        int contactInformationId
        string contactInformationId
        string major
    }
    Course }o--|| ClassSchedule : Includes
    Course {
        int id
        string name
        string description
    }
    ClassSchedule }o--|| Instructor : TaughtBy
    ClassSchedule {
        int id
        int locationId
        int courseId
        int instructorId
        string name
        string description
        string time
    }
    
    Instructor ||--o{ Course : Teaches
    Instructor {
        int id
        int contactInformationId
        string department
    }

    ContactInformation }o--|| Instructor : Has
    ContactInformation }o--|| Student : Has
    ContactInformation {
        int id
        int userId
        string name
        string address
        string email
        string phone
    }

    Location }o--|| ClassSchedule : Has
    Location {
        int id
        string name
        string address
        string phone
    }

    Session }o--|| ClassSchedule : Has
    Session {
        int id
        int locationId
        int courseId
        int instructorId
        string name
        string description
        string time
    }

    Volunteer }o--|| ClassSchedule : Has
    Volunteer {
        int id
        int contactInformationId
        int courseScheduleId
    }

    Review }o--|| Course : Has
    Review {
        int id
        int userId
        int courseId
        int contactInformationId
        string name
        string description
        string rating
    }

    User }o--|| ContactInformation : Has

    User {
        int id
        int contactInformationId
        string userName
        string password
    }
    UserRegistration }o--|| User : Has
    UserRegistration {
        int id
        int userId
    }

    CourseRegistrations }o--|| ClassSchedule : Has
    CourseRegistrations {
        int id
        int userId
        int classScheduleId
    }

```
