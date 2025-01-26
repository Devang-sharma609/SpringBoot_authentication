# Spring Boot Authentication Template 🔐
**I often use this template as reference when I work on Spring Security**
Welcome to the **Spring Boot Authentication** repository! This project demonstrates how to implement user authentication and authorization in a Spring Boot application using **Spring Security**. It provides an example of how to secure your application by managing user credentials, validating logins, and implementing role-based access control.

## Table of Contents 🗂️
- [Introduction](#introduction)
- [Features](#features)
- [Getting Started](#getting-started)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)

## Introduction 🎯
Spring Security is a powerful framework that can be integrated into Spring Boot applications to handle authentication, authorization, and various other security-related tasks. This repository provides a **simple example** of using Spring Security for:

- **User authentication**: Logging in with username/password.
- **JWT token-based authentication**: Secure API access using JSON Web Tokens (JWT).
- **Role-based access control**: Assigning roles like `USER` and `ADMIN` for different access levels.

This project aims to showcase how to implement a secure login flow, protect REST endpoints, and manage roles for users.

## Features ✨
- **Username/Password Authentication**: Secure login system with password hashing.
- **JWT Authentication**: Token-based authentication for stateless security.
- **Role-Based Access**: Restrict access to certain endpoints based on user roles (e.g., `USER`, `ADMIN`).
- **Spring Security**: Fully configured Spring Security setup for securing your application.
- **Secure Password Storage**: BCrypt hashing for user passwords.
- **Customizable Security Configurations**: Easy-to-update Spring Security settings.

## Getting Started 🚀
To get started with this project, you'll need to clone the repository and follow the steps to set up your Spring Boot application.

### Prerequisites 🔧
- Java 11 or higher
- Maven or Gradle
- A database (H2, MySQL, or another DB of your choice)
- Postman or similar tool for testing API endpoints

### Installation ⚙️

1. **Clone the repository**:
    ```bash
    git clone https://github.com/Devang-sharma609/SpringBoot_authentication.git
    ```

2. **Navigate into the project directory**:
    ```bash
    cd SpringBoot_authentication
    ```

3. **Build the project**:
    - Using Maven:
      ```bash
      mvn clean install
      ```
    - Using Gradle:
      ```bash
      gradle build
      ```

4. **Run the application**:
    ```bash
    mvn spring-boot:run
    ```
    or
    ```bash
    gradle bootRun
    ```

Your application should now be running locally (usually at `http://localhost:8080/`).

## Usage ⚡
After setting up the project, you can test the authentication and authorization functionality with the following API endpoints:

- **POST** `/login`: Log in with your username and password to obtain a JWT token.
  
    Example:
    ```bash
    curl -X POST -d "username=user&password=password" http://localhost:8080/login
    ```

    Response:
    ```json
    {
      "token": "your-jwt-token-here"
    }
    ```

- **GET** `/protected`: Access a protected endpoint (only available for authenticated users).

    Example:
    ```bash
    curl -X GET -H "Authorization: Bearer <your-jwt-token>" http://localhost:8080/protected
    ```

- **GET** `/admin`: Access an endpoint that is restricted to `ADMIN` role users.

    Example:
    ```bash
    curl -X GET -H "Authorization: Bearer <your-jwt-token>" http://localhost:8080/admin
    ```

- **POST** `/register`: Register a new user with a username and password.

    Example:
    ```bash
    curl -X POST -d "username=newuser&password=newpassword" http://localhost:8080/register
    ```

## Configuration ⚙️
This project uses Spring Security for user authentication and role-based access control. Key configurations are stored in the `application.properties` or `application.yml` file.

### Example `application.properties`:

```properties
# JWT Token Configuration
jwt.secret=your_jwt_secret_key
jwt.expiration=3600000  # 1 hour

# H2 Database Configuration (For testing purposes)
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=password
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect

# Spring Security Settings
spring.security.user.name=user
spring.security.user.password=password
```

You can customize the JWT secret, expiration time, and database configuration to suit your needs.

## Contributing 🤝
We welcome contributions to this repository! If you'd like to contribute, please follow these steps:

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes.
4. Push your branch to your forked repository.
5. Open a pull request with a description of what you’ve implemented or changed.

Please ensure your code adheres to the standard coding style and includes tests where applicable.

## License 📝
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact
For any queries feel free to mail me at: [Email](https://mailto:devang122indmp@gmail.com)
