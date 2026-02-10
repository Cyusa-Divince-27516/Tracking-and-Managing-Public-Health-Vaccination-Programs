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

1. Get all menu items
2.  Get menu item by ID
3. Filter items by category
4. Filter available items
5. Search items by name
6. Add new menu item
7. Toggle item availability
8. Delete menu item


# 🧱 Technologies Used

-   Java
-   Spring Boot
-   REST API
-   Maven



# 📌 API Base URL

http://localhost:8083/api/menu


# 📖 API Endpoints


## ✅ 1. Get All Menu Items

**Endpoint**

GET /api/menu

**Sample Response (200 OK)**

``` json
[
  {
    "id": 1,
    "name": "Spring Rolls",
    "description": "Crispy appetizer",
    "price": 5.0,
    "category": "Appetizer",
    "available": true
  }
]
```

**Sample Request and Response from Postman (200 OK)**

![Get All menu](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/Get%20Menu%20Items.png)

------------------------------------------------------------------------

## ✅ 2. Get Menu Item by ID

**Endpoint**

GET /api/menu/{id}

Endpoint 

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


**Success Response (200 OK)**

![Get All menu By Id](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/Get%20Item%20By%20id.png).


------------------------------------------------------------------------

## ✅ 3. Get Items by Category

GET /api/menu/category/{category}

Example:

GET /api/menu/category/appetizer

![Get All menu By Category](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/Get%20Menu%20By%20Category.png).

## ✅ 4. Get Available Items

GET /api/menu/available?available=true

![Get menu By Category](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/Get%20Available%20Items.png).

## ✅ 5. Search Menu Items by Name

GET /api/menu/search?name={name}

Example:

GET /api/menu/search?name=spring rolls

![Seaerch Item By name](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/Search%20BY%20Name.png).

## ✅ 6. Add New Menu Item

![Add new Item](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/Add%20New%20Item.png).


## ✅ 7. Toggle Availability

![Toggle Item Availability](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/Toogle%20Item%20Availability.png).

------------------------------------------------------------------------

## ✅ 8. Delete Menu Item

![Delete Item](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/Delete%20Item%20By%20Id.png).

------------------------------------------------------------------------

# ▶️ How to Run the Application

## 1. Open Project

Open in:

-   VS Code
  

## 2. Run Spring Boot Application

Run the main class:
or using Maven:

mvn spring-boot:run

## 3. Test API

http://localhost:8083/api/menu

------------------------------------------------------------------------

# 🧪 Testing Tools

-   Postman 
------------------------------------------------------------------------



# 👨‍💻 Author : Cyusa Divince

Developed for learning REST API development using Spring Boot.
