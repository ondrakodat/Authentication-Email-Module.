# Spring Boot Authentication Module

A reusable authentication and account management module built with Java and Spring Boot.

The project provides secure user authentication, registration, password recovery and email communication. It is designed to be reusable across different Spring Boot applications.

## Features

- User registration
- User login and logout
- JWT-based authentication
- RSA-based JWT signing
- Secure password hashing using Argon2
- HttpOnly authentication cookies
- CSRF protection
- Remember Me functionality
- Password recovery via email
- Six-digit password reset codes
- Reset code expiration and secure validation
- Request rate limiting
- Input validation
- Centralized exception handling

## Technologies

| Technology | Purpose |
|---|---|
| Java 25 | Programming language |
| Spring Boot 4.1.1 | Backend framework |
| Spring Security | Authentication and authorization |
| Spring Data JPA | Database access |
| PostgreSQL | Relational database |
| JWT | Token-based authentication |
| RSA | Asymmetric token signing |
| Argon2 | Password hashing |
| MapStruct | DTO mapping |
| Jakarta Validation | Input validation |
| Spring Mail | Email communication |
| Maven | Dependency management |
| Docker | Database containerization |

## Security

The module implements several security mechanisms:

- Passwords are hashed using Argon2.
- JWT tokens are signed using RSA keys.
- Authentication tokens are stored in HttpOnly cookies.
- CSRF protection is enabled for state-changing requests.
- Password reset codes are securely generated and hashed.
- Reset codes expire after a limited period.
- Rate limiting helps prevent brute-force attacks.

## Password Recovery Workflow

1. User requests a password reset.
2. The application generates a six-digit verification code.
3. The code is hashed and stored with an expiration timestamp.
4. An email containing the verification code is sent to the user.
5. The user submits the code and a new password.
6. The application validates the code and updates the password.

## Project Structure

The application follows a modular architecture:

- `domain` – Domain entities and business models.
- `application` – Application services and business logic.
- `infrastructure` – Database, email and external integrations.
- `api` – REST controllers and API configuration.

## Configuration

Sensitive configuration values are provided through environment variables.

Example:

```properties
spring.datasource.password=${DB_PASSWORD}

app.jwt.private-key-path=${JWT_PRIVATE_KEY_PATH}
app.jwt.public-key-path=${JWT_PUBLIC_KEY_PATH}
```

Never commit passwords, private keys, email credentials or other sensitive configuration values to the repository.

## Purpose

This project was developed as a reusable authentication module to demonstrate practical knowledge of Java, Spring Boot, Spring Security, JWT authentication, password security and backend application architecture.

## Needs to implements Rate Limiter with Redis 
