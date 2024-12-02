**Blog Application API**

A **Spring Boot Blog Application API** that provides user authentication, role-based access control, and functionality for managing blog posts and comments. This project uses **JWT authentication** for securing endpoints.

---

## 🚀 Features

- **Authentication and Authorization**:
  - User signup and login with **JWT**.
  - Role-based access control (`ROLE_USER`, `ROLE_ADMIN`).
- **CRUD Operations**:
  - Manage blog posts and comments.
  - Secure admin-only operations (e.g., delete posts).
- **Database**:
  - Relational database integration using **Spring Data JPA**.
- **Password Security**:
  - Password encryption with **BCrypt**.

---

## 🛠️ Technology Stack

- **Backend**: Spring Boot, Spring Security
- **Authentication**: JSON Web Tokens (JWT)
- **Database**: MySQL, Hibernate (JPA)
- **Build Tool**: Maven
- **Java Version**: Java 17

---

## 📖 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/blog-application.git
cd blog-application
```

### 2. Set Up the Database
- Create a MySQL database (e.g., `blogdb`).
- Configure the database details in `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/blogdb
spring.datasource.username=your-username
spring.datasource.password=your-password

# Hibernate settings
spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
```

### 3. Build and Run the Project
- Build the project:
  ```bash
  mvn clean install
  ```
- Run the application:
  ```bash
  mvn spring-boot:run
  ```

### 4. Access the Application
- API Endpoints start at: [http://localhost:8080/api/](http://localhost:8080/api/)

---

## 📚 API Endpoints

### Authentication Endpoints
| Method | Endpoint          | Description          |
|--------|-------------------|----------------------|
| POST   | `/api/auth/signup`| Register a new user  |
| POST   | `/api/auth/signin`| Login and get a JWT  |

### Post Management
| Method   | Endpoint              | Description                |
|----------|-----------------------|----------------------------|
| GET      | `/api/posts`          | Get all posts              |
| GET      | `/api/posts/{id}`     | Get a single post          |
| POST     | `/api/posts`          | Create a new post          |
| PUT      | `/api/posts/{id}`     | Update an existing post    |
| DELETE   | `/api/posts/{id}`     | Delete a post (admin-only) |

### Comment Management
| Method   | Endpoint                            | Description                   |
|----------|-------------------------------------|-------------------------------|
| GET      | `/api/posts/{postId}/comments`      | Get comments for a post       |
| POST     | `/api/posts/{postId}/comments`      | Add a comment to a post       |
| DELETE   | `/api/posts/{postId}/comments/{id}` | Delete a comment (admin-only) |

---

## 🔒 Security

- JWT-based authentication.
- Role-based access control with `ROLE_USER` and `ROLE_ADMIN`.

---

## 🛠️ Configuration

### Application Properties
Configure the following in `src/main/resources/application.properties`:

```properties
# JWT configuration
app.jwt-secret=your-secret-key
app.jwt-expiration-milliseconds=604800000  # 7 days

# Database configuration
spring.datasource.url=jdbc:mysql://localhost:3306/blogdb
spring.datasource.username=your-username
spring.datasource.password=your-password
```

---

## 🛡️ Testing

- Use **Postman** or any other API testing tool to test the APIs.
- Add the JWT token to the `Authorization` header for protected endpoints:
  ```
  Bearer <your-jwt-token>
  ```

---

## 🤝 Contributing

Contributions are welcome! Please fork the repository and submit a pull request.
