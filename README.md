# Employee Management Application Using Hibernate JPA

This project is a console-based Employee Management Application built with Java, Hibernate JPA, and MySQL. It demonstrates common CRUD (Create, Read, Update, Delete) operations on Employee records using a layered architecture that separates concerns into Controller, DAO, and DTO packages.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Setup Instructions](#setup-instructions)
- [Running the Application](#running-the-application)
- [Configuration Details](#configuration-details)
- [Future Enhancements](#future-enhancements)
- [License](#license)
- [Contact](#contact)

## Overview

The Employee Management Application allows you to:
- Save a new employee record.
- Update an existing employee.
- Find an employee by ID.
- Delete an employee account by ID.
- Verify an employee account using various criteria (ID, phone, or email along with password).
- Display employee details based on joining date, salary, or designation.

The application uses Java Persistence API (JPA) with Hibernate as the provider. It interacts with a MySQL database to persist employee data.

## Features

- **CRUD Operations:**  
  Implemented via a DAO layer using JPA.
- **Console-Based Menu:**  
  A simple text-based interface in the Controller package to interact with the application.
- **Validation and Verification:**  
  Methods to verify employee accounts using ID, phone, or email combined with password.
- **Custom Queries:**  
  Examples include fetching employees based on joining date, salary, and designation.

## Project Structure

Below is the project structure diagram:

```plaintext
EmployeeManagementApplicationUsingHibernateJPA/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   ├── EmployeeManagement_Controller/
│   │   │   │   └── EmployeeManagementController.java
│   │   │   ├── EmployeeManagement_DAO/
│   │   │   │   └── EmployeeDao.java
│   │   │   └── EmployeeManagement_DTO/
│   │   │       └── Employee.java
│   │   └── resources/
│   │       └── META-INF/
│   │           └── persistence.xml
│   └── test/
│       └── (Test files, if any)
├── pom.xml
└── README.md
```


- **EmployeeManagement_Controller:**  
  Contains the main controller (`EmployeeManagementController.java`) with the console menu.
- **EmployeeManagement_DAO:**  
  Contains the data access object (`EmployeeDao.java`) implementing CRUD operations using JPA.
- **EmployeeManagement_DTO:**  
  Contains the Employee entity (`Employee.java`) annotated as a JPA entity.
- **persistence.xml:**  
  Configures the JPA persistence unit, database connection, and Hibernate properties.
- **pom.xml:**  
  Maven configuration file that manages project dependencies.

## Prerequisites

- **Java JDK 8 or higher**
- **Maven** (for build and dependency management)
- **MySQL Server** (ensure MySQL is installed and running)
- **MySQL Connector/J** (automatically managed via Maven dependency)

## Setup Instructions

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/your-username/EmployeeManagementApplicationUsingHibernateJPA.git
   cd EmployeeManagementApplicationUsingHibernateJPA
   ```

2. **Database Setup:**

   The application uses a MySQL database named `Employee_Management`. The persistence unit is configured to create the database if it does not exist:
   
   - Check the `persistence.xml` file under `src/main/resources/META-INF/` for the JDBC URL:
   
     ```xml
     <property name="javax.persistence.jdbc.url" value="jdbc:mysql://localhost:3306/Employee_Management?createDatabaseIfNotExist=true" />
     ```
   
   - Ensure that MySQL is running and the credentials (user: `root`, password: `charantej@@18`) are correct. Modify these values in `persistence.xml` if needed.

3. **Build the Project:**

   Use Maven to compile the project and download dependencies:

   ```bash
   mvn clean install
   ```

## Running the Application

After a successful build, you can run the application using your IDE or from the command line. For example, to run the main class from the command line:

```bash
mvn exec:java -Dexec.mainClass="EmployeeManagement_Controller.EmployeeManagementController"
```

This will launch the console menu for the Employee Management Application.

## Configuration Details

- **JPA and Hibernate:**  
  The persistence unit is defined in `persistence.xml` with the following key properties:
  - **Driver:** `com.mysql.cj.jdbc.Driver`
  - **JDBC URL:** `jdbc:mysql://localhost:3306/Employee_Management?createDatabaseIfNotExist=true`
  - **Dialect:** `org.hibernate.dialect.MySQL8Dialect`
  - **DDL Auto:** `update` (automatically updates the database schema based on entity mappings)
  - **SQL Logging:** Enabled via `hibernate.show_sql` and formatted via `hibernate.format_sql`

- **Maven Dependencies:**  
  The `pom.xml` includes dependencies for Hibernate Core and MySQL Connector/J.

## Future Enhancements

- **Advanced Validation:**  
  Add more robust validation and error handling.
- **Web Interface:**  
  Implement a web-based interface using Spring Boot.
- **Unit Testing:**  
  Add unit tests to ensure each functionality works as expected.
- **External Configuration:**  
  Externalize database credentials and other settings using properties files or environment variables.

## License

This project is licensed under the [MIT License](LICENSE).

## Contact

For any questions or feedback, please contact:
- **Email:** [charantej@gmail.com](mailto:charantejdonthireddy@gmail.com)
```

