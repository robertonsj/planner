# Trip Planner
This web application aims to help users organize trips for work or leisure. 

## Requirements
The user can create a trip with name, start and end date. 
The user can plane their trip adding activities to do every single day.

### Functional requirements
1. The user registers a trip by entering the destination, start and end date, guests' e-mails, and also their full name and email address;
2. The trip creator confirms in the new event by clicking on a link sent by email. The guests receive an email to confirming their attendance, and then the trip creator is redirected to the trip page;
3. The guests, after confirming their attendance by clicking on the link set by e-mail, are redirected to the application in which can entering their name. Their emails will have already been set;
4. In the trip page, the participants will be able to add important links of the trip like AirBnB reservation, places to visit, and so on.
5. Still on the event page, the creator and guests can add activities that will take place during the trip, with title, and start and end date.
6. New participants can be invited in the event page by their e-mails, and must go through the same confirmation flow as any other guest. 

## The Programming Project
- Create the project using Spring Initializr: Spring Web, Flyway, Dev Tools, Lombok, JPA, H2 Database;
- Set database inside the application;
### Migration for TRIPS table
- Migration files represent changes in the database structure: creating table, modifying table (removing or adding fields), installing driver, massive data entry;
- Migration files: SQL scripts, running comands inside database.

### Create Entities that Represent a TRIP
- Create Trip entity repository;
- Create trip registration endpoint; POST/trips
- Create trip query endtpoint; GET/trips/{tripId}

### TRIP Entity
``` Javascript
    "destination": {
      "type": "string",
      "minLength": 4,
      "description": "O destino da viagem."
    },
    "starts_at": {
      "type": "string",
      "format": "date-time",
      "description": "A data e hora de início da viagem no formato RFC 3339."
    },
    "ends_at": {
      "type": "string",
      "format": "date-time",
      "description": "A data e hora de término da viagem no formato RFC 3339."
    },
    "emails_to_invite": {
      "type": "array",
      "items": {
        "type": "string",
        "format": "email"
      },
      "description": "Uma lista de emails a serem convidados para a viagem."
    },
    "owner_name": {
      "type": "string",
      "description": "O nome do proprietário da viagem."
    },
    "owner_email": {
      "type": "string",
      "format": "email",
      "description": "O email do proprietário da viagem."
    }
```
