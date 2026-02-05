# Spring Security Auth API

A production-style **REST API** built with **Spring Boot** that implements a complete authentication and authorization flow using **Spring Security**, **JWT**, and **role-based access control**.

This project focuses on **clean architecture**, **security best practices**, and **real-world backend patterns**, serving both as a learning reference and a professional portfolio piece.

---

## Overview

Authentication and authorization are critical concerns in modern backend systems.  
This project demonstrates how to design and implement a secure API by separating concerns, enforcing proper access control, and following industry-standard security practices.

The application exposes protected endpoints that require JWT authentication and enforces authorization rules based on user roles.

---

## Key Features

- Stateless authentication using JWT  
- Role-based authorization (ADMIN / BASIC)  
- Secure password hashing  
- Token validation via Spring Security filters  
- Protected and public API endpoints  
- Persistent storage with MySQL  
- JPA / Hibernate ORM  
- Automatic schema generation  
- Initial data loading with SQL scripts  

---

## Tech Stack

- **Java 25**
- **Spring Boot**
- **Spring Security**
- **Spring Data JPA**
- **JWT (JSON Web Tokens)**
- **Hibernate**
- **MySQL**
- **Maven**

---

## Architecture

The project follows a layered architecture with clear responsibility boundaries:

```text
src/main/java
├── config        # Application and security configuration
├── controllers   # REST controllers (API layer)
├── entities      # JPA entities (domain model)
├── repositories  # Data access layer
├── services      # Business logic
└── security      # Authentication, authorization, and filters
```

This structure improves maintainability, testability, and scalability.

---

## Authentication & Authorization Flow

1. A user authenticates using valid credentials  
2. The system validates the credentials  
3. A JWT token is generated and returned  
4. The client must include the token in subsequent requests:

```http
Authorization: Bearer <JWT_TOKEN>
```

5. Access is granted or denied based on the user’s roles and endpoint rules  

---

## Environment Configuration

Sensitive configuration values are externalized.

Create a `.env` file in the project root (this file is **not committed to Git**):

```env
DB_URL=jdbc:mysql://localhost:3306/mydb
DB_USER=root
DB_PASSWORD=your_password
JWT_SECRET=your_secret_key
```

---

## Running the Application

### Prerequisites
- Java 25  
- MySQL 8+  
- Maven  

### Steps

```bash
# Clone the repository
git clone https://github.com/john-dalmolin/spring-security-auth-api.git

# Navigate to the project directory
cd spring-security-auth-api

# Run the application
./mvnw spring-boot:run
```

The API will be available at:

```text
http://localhost:8080
```

---

## Database

- Database schema is generated automatically by Hibernate  
- Initial roles are inserted using `data.sql`  
- Relationships are managed via JPA annotations  

---

## Security Considerations

- Passwords are stored using secure hashing  
- JWT tokens are validated on every request  
- No sensitive data is committed to version control  
- Access control is enforced at the endpoint level  

---

## Purpose

This project was created to demonstrate:

- Secure API design  
- Proper use of Spring Security  
- Authentication vs Authorization concepts  
- Clean backend architecture  
- Real-world development practices  

---

## Author

**John Dalmolin**  
Backend / Full Stack Developer  

GitHub: https://github.com/john-dalmolin  

---

## License

This project is provided for educational and portfolio purposes.
