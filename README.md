# Todo Web Application

A Spring Boot web application for managing personal todos. Users can sign in, create tasks, choose target dates from a calendar, update existing tasks, and delete completed or unwanted tasks.

## Features

- Form-based authentication with Spring Security
- Create, view, update, and delete todos
- Target-date validation and calendar date picker
- JSP views styled with Bootstrap
- Per-user todo filtering
- Spring Data JPA persistence
- In-memory H2 database and browser console

## Technology stack

- Java 21
- Spring Boot 4.1.1
- Spring MVC
- Spring Security
- Spring Data JPA
- JSP and JSTL
- H2 Database
- Bootstrap 5, jQuery, and Bootstrap Datepicker
- Maven Wrapper

## Run locally

### Prerequisites

- JDK 21
- No separate Maven installation is required; the Maven Wrapper is included.

### Start the application

On Windows:

```powershell
.\mvnw.cmd spring-boot:run
```

On macOS or Linux:

```bash
./mvnw spring-boot:run
```

Open [http://localhost:8080](http://localhost:8080) and sign in with:

- Username: `Swayam`
- Password: `1`

These credentials are intended for local demonstration only.

## H2 database console

While the application is running, open [http://localhost:8080/h2-console](http://localhost:8080/h2-console) and use:

| Setting | Value |
| --- | --- |
| JDBC URL | `jdbc:h2:mem:testdb` |
| User name | `sa` |
| Password | Leave blank |

Because the database is stored in memory, todo data is cleared whenever the application stops.

## Test

On Windows:

```powershell
.\mvnw.cmd test
```

On macOS or Linux:

```bash
./mvnw test
```

## Main routes

| Route | Purpose |
| --- | --- |
| `/` | Welcome page |
| `/list-todos` | List the signed-in user's todos |
| `/add-todo` | Create a todo |
| `/update-todo?id={id}` | Update a todo |
| `/delete-todos?id={id}` | Delete a todo |
| `/h2-console` | Inspect the in-memory database |

## Project structure

```text
src/main/java
  .../login       Welcome controller
  .../security    Spring Security configuration
  .../todo        Todo entity, repository, and controller
src/main/resources
  application.properties
  META-INF/resources/WEB-INF/jsp
                  JSP pages and shared fragments
```
