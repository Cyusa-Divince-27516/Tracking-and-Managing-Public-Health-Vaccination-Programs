# Question 2 - Student Registration API

A Spring Boot REST API for managing student registration and information. This application provides endpoints to retrieve students, search by major, filter by GPA, register new students, and update existing 
student records. Screenshots from Postman can be added for each endpoint request and response.

------------------------------------------------------------------------

## Table of Contents

-   Overview
-   Technology Stack
-   Project Structure
-   Getting Started
-   API Endpoints
-   Running the Application
-   Configuration

------------------------------------------------------------------------

## Overview

This is a simple REST API built using Spring Boot that manages student
registration and information. The API supports:

-   Retrieve all students
-   Retrieve student by ID
-   Search students by major
-   Filter students by GPA
-   Register new students
-   Update existing student information

## Technology Stack

-   Java
-   Spring Boot
-   Maven
-   Server Port: 8082

------------------------------------------------------------------------

## Project Structure

    QUESTION2-STUDENT-API/
    ├── .mvn/
    │   └── wrapper/
    ├── src/
    │   ├── main/
    │   │   ├── java/registration/com/question2_student_api/
    │   │   │   ├── Question2StudentApiApplication.java
    │   │   │   └── Controller/
    │   │   │       ├── StudentController.java
    │   │   │       └── Student.java
    │   │   └── resources/
    │   │       ├── static/
    │   │       ├── templates/
    │   │       └── application.properties
    │   └── test/
    ├── target/
    ├── pom.xml
    ├── mvnw
    └── mvnw.cmd

------------------------------------------------------------------------

## Getting Started

### Prerequisites

-   Java installed (JDK 17 or higher recommended)
-   Maven installed OR use Maven Wrapper included in project
-   IDE (VS Code / IntelliJ)

------------------------------------------------------------------------

## API Endpoints

### 1. Get All Students

Endpoint: GET /api/students

Sample Request: GET http://localhost:8082/api/students

Sample Response:

``` json
[
  {
    "studentId": 1,
    "firstName": "John",
    "lastName": "Doe",
    "email": "john@mail.com",
    "major": "Computer Science",
    "gpa": 3.5
  }
]
```

![Get All Students](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/students/Get%20All%20Students.png).

------------------------------------------------------------------------

### 2. Get Student by ID

Endpoint: GET /api/students/{studentId}

Sample Request: GET http://localhost:8082/api/students/1

Sample Response:

``` json
{
  "studentId": 1,
  "firstName": "John",
  "lastName": "Doe",
  "email": "john@mail.com",
  "major": "Computer Science",
  "gpa": 3.5
}
```

![Get Student By Id](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/students/Get%20Student%20By%20Id.png).

------------------------------------------------------------------------

### 3. Get Students by Major

Endpoint: GET /api/students/major/{major}

Sample Request: GET http://localhost:8082/api/students/major/Computer
Science

Sample Response:

``` json
[
  {
    "studentId": 1,
    "firstName": "John",
    "lastName": "Doe",
    "email": "john@mail.com",
    "major": "Computer Science",
    "gpa": 3.5
  }
]
```

![Get Student By Major](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/students/Get%20Student%20By%20Major.png).

------------------------------------------------------------------------

### 4. Filter Students by GPA

Endpoint: GET /api/students/filter?gpa={minGpa}

Sample Request: GET http://localhost:8082/api/students/filter?gpa=3.0

Sample Response:

``` json
[
  {
    "studentId": 2,
    "firstName": "Alice",
    "lastName": "Smith",
    "email": "alice@mail.com",
    "major": "Information Systems",
    "gpa": 3.8
  }
]
```

![Get Student By Filtering GPA](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/students/Get%20Student%20By%20GPA.png)

------------------------------------------------------------------------

### 5. Register New Student

Endpoint: POST /api/students

Sample Request: POST http://localhost:8082/api/students Content-Type:
application/json

``` json
{
  "studentId": 6,
  "firstName": "Kevin",
  "lastName": "Jean",
  "email": "kevin@mail.com",
  "major": "Software Engineering",
  "gpa": 3.7
}
```

Sample Response:

``` json
{
  "studentId": 6,
  "firstName": "Kevin",
  "lastName": "Jean",
  "email": "kevin@mail.com",
  "major": "Software Engineering",
  "gpa": 3.7
}
```

![Register New Student](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/students/Register%20New%20Student.png)

------------------------------------------------------------------------

### 6. Update Student Information

Endpoint: PUT /api/students/{studentId}

Sample Request: PUT http://localhost:8082/api/students/1 Content-Type:
application/json

``` json
{
  "firstName": "Updated",
  "lastName": "Student",
  "email": "updated@mail.com",
  "major": "Computer Science",
  "gpa": 3.9
}
```

Sample Response:

``` json
{
  "studentId": 1,
  "firstName": "Updated",
  "lastName": "Student",
  "email": "updated@mail.com",
  "major": "Computer Science",
  "gpa": 3.9
}
```

![Update Student Information](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/students/Update%20Student%20Information.png)

------------------------------------------------------------------------

## Running the Application

Windows:

    mvn spring-boot:run


Application URL: http://localhost:8082

------------------------------------------------------------------------

## API Response Codes

| Status Code | Description |
|-------------|-------------|
| 200 | OK - Request successful |
| 201 | Created - Resource created successfully |
| 404 | Not Found - Resource not found |
| 400 | Bad Request - Invalid request parameters |
| 500 | Internal Server Error - Server error |


------------------------------------------------------------------------

## Configuration

src/main/resources/application.properties

``` properties
spring.application.name=question2-student-api
server.port=8082
```

------------------------------------------------------------------------

## Author

Cyusa Divince
