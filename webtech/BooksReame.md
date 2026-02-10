# Question 1 - Library API

A Spring Boot REST API for managing a library's book collection. This application provides endpoints to retrieve, search, add, and delete books from the library by providing Books api screenshot from Postman.

## Table of Contents

- [Overview](#overview)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [API Endpoints](#api-endpoints)
- [Running the Application](#running-the-application)
- [Testing the Endpoints](#testing-the-endpoints)

## Overview

This is a simple REST API built with Spring Boot that manages a collection of books. The API supports CRUD operations (Create, Read, Update, Delete) and search functionality for books in the library.

## Technology Stack

- **Java**: Version 21
- **Spring Boot**: Version 4.0.2
- **Build Tool**: Maven 3.9.12
- **Server Port**: 8081

## Project Structure

``` 
question1-library-api/
├── src/
│   ├── main/
│   │   ├── java/library/com/question1_library_api/
│   │   │   ├── Question1LibraryApiApplication.java
│   │   │   └── Controller/
│   │   │       ├── BookController.java
│   │   │       ├── Book.java
│   │   │
│   │   └── resources/
│   │       └── application.properties
│   └── test/
│       └── java/library/com/question1_library_api/
│           └── Question1LibraryApiApplicationTests.java
├── pom.xml
├── mvnw
└── mvnw.cmd
```

## Getting Started

### Prerequisites

- Java 21 or higher installed
- Maven 3.6.0 or higher (or use the provided Maven wrapper)


The application will start on **http://localhost:8081**

## API Endpoints

### 1. Get All Books

**Endpoint**: `GET /api/books`

**Description**: Retrieve all books in the library.

![Retrieve all books](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/books/Get%20All%20Books.png).
### 2. Get Book by ID

**Endpoint**: `GET /api/books/{id}`

**Description**: Retrieve a specific book by its ID.
![Get Book by Its Id](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/books/Get%20Book%20By%20Id.png).

**Parameters**:
- `id` (path parameter, required): The unique identifier of the book


### 3. Search Books by Title

**Endpoint**: `GET /api/books/search`

**Description**: Search for books by title (case-insensitive, partial matching supported).

**Parameters**:
- `title` (query parameter, required): The title or partial title to search for
![Seaech Book By its title](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/books/Search%20Book%20By%20title.png).

### 4. Add a New Book

**Endpoint**: `POST /api/books`

**Description**: Add a new book to the library.

**Request Body**:
```json
{
  "id": 4,
  "title": "The Clean Code",
  "author": "Robert C. Martin",
  "isbn": "ISBN004",
  "publicationYear": 2008
}
```

**Request**:
```http
POST http://localhost:8081/api/books HTTP/1.1
Content-Type: application/json

{
  "id": 4,
  "title": "The Clean Code",
  "author": "Robert C. Martin",
  "isbn": "ISBN004",
  "publicationYear": 2008
}
```
![Add new Book](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/books/Add%20New%20Book.png).


### 5. Delete a Book

**Endpoint**: `DELETE /api/books/{id}`

**Description**: Delete a book from the library by its ID.

**Parameters**:
- `id` (path parameter, required): The unique identifier of the book to delete

![Delete Book Book](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/books/Delete%20Book.png).




## Running the Application in VS Code

### Option 1: Using Maven Wrapper

**On Windows**:
```
mvn spring-boot:run
```

## API Response Codes

| Status Code | Description |
|-------------|-------------|
| 200 | OK - Request successful |
| 201 | Created - Resource created successfully |
| 404 | Not Found - Resource not found |
| 400 | Bad Request - Invalid request parameters |
| 500 | Internal Server Error - Server error |

---

## Configuration

The application configuration is managed in `src/main/resources/application.properties`:

```properties
spring.application.name=question1-library-api
server.port=8081
```
---

## Author

Cyusa Divince


