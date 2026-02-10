E-Commerce Product API

A professional Spring Boot REST API for managing an e-commerce product catalog. This application provides endpoints to retrieve, filter, search, create, update, and delete products. It demonstrates RESTful
design principles and uses Postman for endpoint testing.

------------------------------------------------------------------------

## Table of Contents

-   Overview
-   Technology Stack
-   Project Structure
-   Getting Started
-   API Endpoints
-   Running the Application
-   API Response Codes
-   Configuration
-   Author

------------------------------------------------------------------------

## Overview

This project is a simple REST API built with Spring Boot that manages a collection of e-commerce products. The API supports:

-   CRUD operations (Create, Read, Update, Delete)
-   Filtering by category and brand
-   Searching by keyword
-   Price range filtering
-   Stock management
-   Pagination support

------------------------------------------------------------------------

## Technology Stack used

-   Java 21 
-   Spring Boot
-   Maven
-   REST API
-   Postman (for testing)

------------------------------------------------------------------------

## Project Structure

    question3-ecommerce-api/
    ├── src/
    │   ├── main/
    │   │   ├── java/Ecommerce/com/question3_Ecommerce/
    │   │   │   ├── Question3EcommerceApiApplication.java
    │   │   │   └── Controller/
    │   │   │       ├── Product.java
    │   │   │       └── ProductController.java
    │   │   └── resources/
    │   │       ├── static/
    │   │       ├── templates/
    │   │       └── application.properties
    │   └── test/
    ├── pom.xml
    ├── mvnw
    └── mvnw.cmd

------------------------------------------------------------------------

## Getting Started

### Prerequisites

-   Java installed 21 or 17
-   Maven installed (or use Maven wrapper)

The application runs on:

http://localhost:8084

------------------------------------------------------------------------

# API Endpoints

------------------------------------------------------------------------

## 1. Get All Products

GET /api/products

Optional Pagination:

GET /api/products?page=0&limit=5

Sample Response:

``` json
[
  {
    "productId": 1,
    "name": "iPhone 14",
    "description": "Apple smartphone",
    "price": 900.0,
    "category": "Electronics",
    "stockQuantity": 10,
    "brand": "Apple"
  }
]
```
![Get All Products](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/ecommerce/Get%20All%20Products.png).

------------------------------------------------------------------------

## 2. Get Product by ID

GET /api/products/{productId}

Example:

GET /api/products/9

![Get Products By Id](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/ecommerce/Get%20Product%20By%20Id.png).

------------------------------------------------------------------------

## 3. Get Products by Category

GET /api/products/category/{category}

![Get Products By Category](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/ecommerce/Get%20Product%20By%20Category.png)

------------------------------------------------------------------------

## 4. Get Products by Brand

GET /api/products/brand/{brand}

![Get Products By Brand](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/ecommerce/Get%20Product%20By%20Brand.png)

------------------------------------------------------------------------

## 5. Search Products

GET /api/products/search?keyword={keyword}

![Search Product By Name](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/ecommerce/Search%20Product%20By%20Name.png)

------------------------------------------------------------------------

## 6. Get Products by Price Range

GET /api/products/price-range?min=100&max=1000

![get Product By Price Range](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/ecommerce/Get%20Product%20By%20Price%20Range.png)

------------------------------------------------------------------------

## 7. Get In-Stock Products

GET /api/products/in-stock

![Get Product in Stock](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/ecommerce/Get%20Product%20Stock.png)

------------------------------------------------------------------------

## 8. Add New Product

POST /api/products

Sample Request:

``` json
{
        "productId": 11,
        "name": "iPhone 17 Promax",
        "description": "Apple smartphone",
        "price": 1900.0,
        "category": "Electronics",
        "stockQuantity": 20,
        "brand": "Apple"
    }
```

![Addd new Product](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/ecommerce/Add%20New%20Product.png)

------------------------------------------------------------------------

## 9. Update Product

PUT /api/products/{productId}

![Update product Details](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/ecommerce/Update%20Product%20Details.png)

------------------------------------------------------------------------

## 10. Update Stock Quantity

PATCH /api/products/{productId}/stock?quantity=20

![Update Stock](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/ecommerce/Update%20Stock%20Quantity.png)

------------------------------------------------------------------------

## 11. Delete Product

DELETE /api/products/9

![Delete Product](https://github.com/Cyusa-Divince-27516/Tracking-and-Managing-Public-Health-Vaccination-Programs/blob/main/images/ecommerce/Delete%20Product.png)

------------------------------------------------------------------------

## Running the Application

Using Maven:

    mvn spring-boot:run

Then open:

http://localhost:8084/api/products

------------------------------------------------------------------------

## API Response Codes

  Status Code   Description
  ------------- -----------------------------------------
  200           OK - Request successful
  201           Created - Resource created successfully
  404           Not Found - Resource not found
  400           Bad Request
  500           Internal Server Error

------------------------------------------------------------------------

## Configuration

Located in:

src/main/resources/application.properties

Example:

``` properties
spring.application.name=question3-ecommerce-api
server.port=8084
```

------------------------------------------------------------------------

## Author

Cyusa Divince
