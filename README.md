# School App (SSR)

A Spring Boot-based Server-Side Rendering (SSR) application for managing school entities, including teachers, users, and roles. The project uses Spring Boot, Thymeleaf for templating, Spring Security for authentication and authorization, and Flyway for database migrations.

## Tech Stack

- **Language:** Java 21 (Amazon Corretto)
- **Framework:** Spring Boot 3.5.12
- **Persistence:** Spring Data JPA, Hibernate, MySQL
- **Migrations:** Flyway
- **Security:** Spring Security
- **Templating:** Thymeleaf
- **Build Tool:** Gradle

## Requirements

- **Java:** JDK 21
- **Database:** MySQL
- **Build Tool:** Gradle (wrapper included)

## Setup and Run

### 1. Database Configuration

Ensure you have a MySQL database instance running. You can configure the database connection via environment variables or by modifying `src/main/resources/application-dev.properties`.

Default database name: `school9ssr`
Default username: `user9`
Default password: `12345`

### 2. Environment Variables

The application supports several environment variables to override default settings:

- `MYSQL_HOST`: Database host (default: `localhost`)
- `MYSQL_PORT`: Database port (default: `3306`)
- `MYSQL_DB`: Database name (default: `school9ssr`)
- `MYSQL_USER`: Database username (default: `user9`)
- `MYSQL_PASSWORD`: Database password (default: `12345`)
- `spring.profiles.active`: Spring profile (e.g., `dev`, `prod`, `staging`)

### 3. Build and Run

To build the project:
```bash
./gradlew build
```

To run the application:
```bash
./gradlew bootRun
```

Or run the JAR file after building:
```bash
java -jar build/libs/schoolapp.jar --spring.profiles.active=dev
```

The application will be accessible at `http://localhost:8080`.

## Scripts

- `./gradlew bootRun`: Runs the application with the development profile.
- `./gradlew build`: Compiles, tests, and packages the application.
- `./gradlew bootJar`: Packages the application into an executable JAR.
- `./gradlew test`: Runs unit and integration tests.

## Tests

Tests are located in `src/test/java`. To execute them, run:
```bash
./gradlew test
```

## Project Structure

```text
schoolapp/
├── gradle/                  # Gradle wrapper configuration
├── src/
│   ├── main/
│   │   ├── java/            # Java source code
│   │   │   └── gr.aueb.cf.schoolapp
│   │   │       ├── authentication   # Security & User Details
│   │   │       ├── controller       # Spring MVC Controllers
│   │   │       ├── core/exceptions  # Custom exception handlers
│   │   │       ├── dto              # Data Transfer Objects
│   │   │       ├── mapper           # Entity-DTO Mappers
│   │   │       ├── model            # JPA Entities
│   │   │       ├── repository       # Spring Data Repositories
│   │   │       ├── service          # Business Logic Services
│   │   │       └── validator        # Custom Validators
│   │   └── resources/       # Configuration and Static Assets
│   │       ├── db/migration # Flyway SQL migrations
│   │       ├── static/      # CSS, JS, Images
│   │       ├── templates/   # Thymeleaf HTML templates
│   │       └── application.properties # Main configuration
│   └── test/                # Unit and Integration tests
├── build.gradle             # Build configuration
└── settings.gradle          # Gradle project settings
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details (if applicable).
