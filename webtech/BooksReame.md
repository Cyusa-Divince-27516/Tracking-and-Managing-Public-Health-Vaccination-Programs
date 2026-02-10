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


### 2. Get Book by ID

**Endpoint**: `GET /api/books/{id}`

**Description**: Retrieve a specific book by its ID.

**Parameters**:
- `id` (path parameter, required): The unique identifier of the book

**Request**:
```http
GET http://localhost:8081/api/books/1 HTTP/1.1
Content-Type: application/json
```

**Response** (200 OK):
```json
{
  "id": 1,
  "title": "Java Basics",
  "author": "calvin klein",
  "isbn": "ISBN001",
  "publicationYear": 2020
}
```

**Response** (404 Not Found - if book doesn't exist):
```json
null
```

---

### 3. Search Books by Title

**Endpoint**: `GET /api/books/search`

**Description**: Search for books by title (case-insensitive, partial matching supported).

**Parameters**:
- `title` (query parameter, required): The title or partial title to search for

**Request**:
```http
GET http://localhost:8081/api/books/search?title=Java HTTP/1.1
Content-Type: application/json
```

**Response** (200 OK):
```json
[
  {
    "id": 1,
    "title": "Java Basics",
    "author": "calvin klein",
    "isbn": "ISBN001",
    "publicationYear": 2020
  }
]
```

**Request** (No results):
```http
GET http://localhost:8081/api/books/search?title=nonexistent HTTP/1.1
```

**Response** (200 OK - Empty array):
```json
[]
```

---

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

**Response** (201 Created):
```json
{
  "id": 4,
  "title": "The Clean Code",
  "author": "Robert C. Martin",
  "isbn": "ISBN004",
  "publicationYear": 2008
}
```

---

### 5. Delete a Book

**Endpoint**: `DELETE /api/books/{id}`

**Description**: Delete a book from the library by its ID.

**Parameters**:
- `id` (path parameter, required): The unique identifier of the book to delete

**Request**:
```http
DELETE http://localhost:8081/api/books/1 HTTP/1.1
Content-Type: application/json
```

**Response** (200 OK - Book deleted):
```json
"Book deleted successfully"
```

**Response** (404 Not Found - Book doesn't exist):
```json
"Book not found"
```

---

## Additional Endpoints

### Get Student Names (Legacy Endpoint)

**Endpoint**: `GET /logins/hello`

**Description**: Retrieve a list of student names.

**Request**:
```http
GET http://localhost:8081/logins/hello HTTP/1.1
```

**Response** (200 OK):
```json
[
  "Eric",
  "Rukundo",
  "Emmanuel",
  "Joy",
  "Munezero"
]
```

---

### Search Student by Name

**Endpoint**: `GET /logins/searchStudents`

**Description**: Search for a student by name.

**Parameters**:
- `student` (query parameter, required): The student name to search for

**Request**:
```http
GET http://localhost:8081/logins/searchStudents?student=Eric HTTP/1.1
```

**Response** (200 OK - Student found):
```
"The student with this name Eric is found"
```

**Response** (200 OK - Student not found):
```
"The student with this name Unknown is not found"
```

---

## Running the Application

### Option 1: Using Maven Wrapper (Recommended)

**On Windows**:
```bash
mvnw.cmd spring-boot:run
```

**On Linux/macOS**:
```bash
./mvnw spring-boot:run
```

### Option 2: Build and Run JAR

**On Windows**:
```bash
mvnw.cmd clean package
java -jar target/question1-library-api-0.0.1-SNAPSHOT.jar
```

**On Linux/macOS**:
```bash
./mvnw clean package
java -jar target/question1-library-api-0.0.1-SNAPSHOT.jar
```

### Option 3: Using IDE

1. Open the project in your IDE (Visual Studio Code, IntelliJ IDEA, Spring Tool Suite)
2. Navigate to `Question1LibraryApiApplication.java`
3. Click the "Run" button or press `Shift+F10` (IntelliJ) / `Ctrl+F5` (VS Code)

---

## Testing the Endpoints

### Using cURL

```bash
# Get all books
curl http://localhost:8081/api/books

# Get book by ID
curl http://localhost:8081/api/books/1

# Search books
curl http://localhost:8081/api/books/search?title=Java

# Add a new book
curl -X POST http://localhost:8081/api/books \
  -H "Content-Type: application/json" \
  -d '{"id":4,"title":"New Book","author":"Author Name","isbn":"ISBN999","publicationYear":2023}'

# Delete a book
curl -X DELETE http://localhost:8081/api/books/1
```

### Using Postman

1. Import the endpoints mentioned above
2. Set the request method (GET, POST, DELETE)
3. Enter the URL (e.g., `http://localhost:8081/api/books`)
4. For POST requests, set the body as JSON
5. Click "Send"

---

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

To change the server port, modify the `server.port` property.

---

## Contributing

Feel free to submit issues and enhancement requests.

---

## Author

Created for AUCA Web Technologies Assignment - Semester 7

---

## License

This project is provided as-is for educational purposes.
