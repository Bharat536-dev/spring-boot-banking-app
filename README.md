# 🏦 Spring Boot Banking App

This is a simple **banking application** built using Spring Boot. It allows users to perform basic account operations like creating, retrieving, depositing into, withdrawing from, and deleting bank accounts. This project is created for **learning purposes** and demonstrates core concepts of Spring Boot such as REST APIs, service layering, exception handling, and integration with a MySQL database.

---

## 🚀 Features

- Create a new bank account
- Retrieve a specific account by ID
- View all bank accounts
- Deposit money into an account
- Withdraw money from an account
- Delete an account
- Exception handling with global error responses
- DTO pattern and service-implementation layering

---

## 🛠 Tech Stack

- Java 17+
- Spring Boot
    - Spring Web
    - Spring Data JPA
- Lombok
- MySQL
- Maven
- Postman (for API testing)

---

## 📦 Project Structure

src
└── main
├── java
│ └── com.bharat.banking
│ ├── controller
│ ├── dto
│ ├── entity
│ ├── exception
│ ├── mapper
│ ├── repository
│ ├── service
│ └── service.impl
└── resources
└── application.properties


---

## 📡 API Endpoints

| Method | Endpoint                     | Description                    |
|--------|------------------------------|--------------------------------|
| POST   | `/api/accounts`              | Create a new account           |
| GET    | `/api/accounts/{id}`         | Get account by ID              |
| GET    | `/api/accounts`              | Get all accounts               |
| PUT    | `/api/accounts/{id}/deposit` | Deposit amount into account    |
| PUT    | `/api/accounts/{id}/withdraw`| Withdraw amount from account   |
| DELETE | `/api/accounts/{id}`         | Delete account by ID           |

> **Note**: Use Postman to test the above endpoints.

---

## ⚙️ Setup Instructions

### 1. Clone the repository
```bash
git clone https://github.com/Bharat536-dev/spring-boot-banking-app.git
cd spring-boot-banking-app


2. Set up the MySQL Database
Create a database named banking_app (or update the name in application.properties).

sql
Copy
Edit
CREATE DATABASE banking_app;
3. Configure application.properties
ini
Copy
Edit
# Database configuration
spring.datasource.url=jdbc:mysql://localhost:3306/banking_app
spring.datasource.username=your_mysql_username
spring.datasource.password=your_mysql_password

# JPA settings
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
4. Run the Application
From IntelliJ: Run BankingAppApplication.java

Or use terminal:

bash
Copy
Edit
./mvnw spring-boot:run
App will run on: http://localhost:8080

❗ Sample Postman Payloads
Create Account (POST /api/accounts)
json
Copy
Edit
{
  "accountHolderName": "John Doe",
  "balance": 1000.00
}
Deposit (PUT /api/accounts/1/deposit)
json
Copy
Edit
{
  "amount": 500.00
}
Withdraw (PUT /api/accounts/1/withdraw)
json
Copy
Edit
{
  "amount": 200.00
}


❌ Error Handling
All exceptions are handled globally using @ControllerAdvice. You’ll get clear error messages in JSON format for bad requests or invalid operations.



📚 Purpose
This project was created to learn and practice Spring Boot fundamentals, including REST APIs, service-repository architecture, exception handling, and integration with MySQL.

