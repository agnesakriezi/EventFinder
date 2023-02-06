# EventFinder
Event Finder is a platform for users to discover and search for events happening in their area. The platform allows users to search for events based on date, location, and category.

System Requirements
Table of Contents
Prerequisites
Build and Run
Architecture
APIs
Database

1. Prerequisites
Java 8 or higher
Gradle 6.0 or higher
MySQL 8.0 or higher
An IDE such as IntelliJ IDEA or Eclipse

2. Build and Run
Clone the repository: git clone https://github.com/<your-username>/EventFinder.git
Import the project into your IDE.
Open a terminal in the project directory and run the following command to build the application:
Copy code
gradle build
Start the application by running the following command:
Copy code
gradle bootRun

3. Architecture
The EventFinder application is built using the Java Spring Boot framework. It follows the Model-View-Controller (MVC) design pattern.
The model represents the data and business logic of the application. It communicates with the database to store and retrieve data.
The view represents the user interface of the application. It displays the data received from the controller.
The controller handles the user interactions and requests. It communicates with the model to retrieve the data and send it to the view.

4. APIs
The application exposes the following REST APIs:

/api/events: Retrieve a list of all events.
/api/events/{id}: Retrieve a specific event by its ID.
/api/events: Create a new event.
/api/events/{id}: Update an existing event.
/api/events/{id}: Delete an event.

5. Database
The EventFinder application uses a MySQL database to store event information. The database can be set up using the following SQL script:

sql
Copy code
CREATE DATABASE eventfinder;

USE eventfinder;

CREATE TABLE events (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(255) NOT NULL,
  description VARCHAR(255) NOT NULL,
  start_date DATE NOT NULL,
  end_date DATE NOT NULL
);
The application connects to the database using the application.properties file in the src/main/resources directory. You need to update the following properties with your database information:

bash
Copy code
spring.datasource.url=jdbc:mysql://localhost:3306/eventfinder
spring.datasource.username=<your-username>
spring.datasource.password=<your-password>
