# 🍽️ Restaurant Menu API

A simple RESTful API built with **Spring Boot** for managing a
restaurant menu system.

This project demonstrates:

-   CRUD operations
-   Filtering and searching
-   Query parameters
-   HTTP status handling
-   Clean controller logic using ResponseEntity

# 🚀 Features

1. Get all menu items\
2.  Get menu item by ID\
3. Filter items by category\
4. Filter available items\
5. Search items by name\
6. Add new menu item\
7. Toggle item availability\
8. Delete menu item


# 🧱 Technologies Used

-   Java
-   Spring Boot
-   REST API
-   Maven



# 📌 API Base URL

http://localhost:8080/api/menu


# 📖 API Endpoints


## ✅ 1. Get All Menu Items

**Endpoint**

GET /api/menu

**Sample Request and Response from Postman (200 OK)**

![Get All menu](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/Get%20Menu%20Items.png)

------------------------------------------------------------------------

## ✅ 2. Get Menu Item by ID

**Endpoint**

GET /api/menu/{id}

**Example**

GET /api/menu/1

**Success Response (200 OK)**

``` json
{
  "id": 1,
  "name": "Spring Rolls",
  "description": "Crispy appetizer",
  "price": 5.0,
  "category": "Appetizer",
  "available": true
}
```

**Error Response (404 NOT FOUND)**

Item not found

------------------------------------------------------------------------

## ✅ 3. Get Items by Category

GET /api/menu/category/{category}

Example:

GET /api/menu/category/Appetizer

------------------------------------------------------------------------

## ✅ 4. Get Available Items

GET /api/menu/available?available=true

------------------------------------------------------------------------

## ✅ 5. Search Menu Items by Name

GET /api/menu/search?name={name}

Example:

GET /api/menu/search?name=pizza

------------------------------------------------------------------------

## ✅ 6. Add New Menu Item

POST /api/menu

**Sample Request**

``` json
{
  "id": 9,
  "name": "Burger",
  "description": "Beef burger",
  "price": 9.5,
  "category": "Main Course",
  "available": true
}
```

Response:

201 CREATED

------------------------------------------------------------------------

## ✅ 7. Toggle Availability

PUT /api/menu/{id}/availability

Example:

PUT /api/menu/1/availability

This switches:

true → false\
false → true

------------------------------------------------------------------------

## ✅ 8. Delete Menu Item

DELETE /api/menu/{id}

Example:

DELETE /api/menu/1

Response:

200 OK - Item deleted\
404 NOT FOUND - Item not found

------------------------------------------------------------------------

# ▶️ How to Run the Application

## 1️⃣ Clone Repository

git clone https://github.com/YOUR_USERNAME/restaurant-menu-api.git

## 2️⃣ Open Project

Open in:

-   IntelliJ IDEA
-   VS Code
-   Eclipse

## 3️⃣ Run Spring Boot Application

Run the main class:

Application.java

or using Maven:

mvn spring-boot:run

## 4️⃣ Test API

http://localhost:8080/api/menu

------------------------------------------------------------------------

# 🧪 Testing Tools

-   Postman
-   Thunder Client (VS Code)
-   Browser (for GET requests)

------------------------------------------------------------------------

# 📂 Project Structure

src └── main └── java └── demo.rw ├── MenuItem.java └──
MenuController.java

------------------------------------------------------------------------

# 👨‍💻 Author

Developed for learning REST API development using Spring Boot.
