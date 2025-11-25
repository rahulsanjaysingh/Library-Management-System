# 📚 Library Management System

A desktop-based **Library Management System** built using **Java Swing**, **JDBC**, and **MySQL**.  
This project demonstrates practical knowledge of DBMS, SQL, JDBC operations, GUI design, event handling, validation, and CRUD operations.  

Designed for academic submission, but structured cleanly for future expansion.

---

## 📌 Overview

The application provides an interactive desktop UI to manage:

- **Books**
- **Members**
- **Issue & Return transactions**
- **Date handling and record tracking**
- **MySQL-based persistent storage**

The code demonstrates:

- Java Swing (`JFrame`, `JTable`, `JPanel`, `EventListeners`)  
- JDBC connectivity (CRUD operations)  
- MySQL relational operations  
- Input validation using regex  
- DAO-like separation (DB helper functions)  
- Multi-screen navigation inside a single JFrame  

---

## 📂 Project Structure

LibraryManagementSystem/
│
├── src/
│ ├── LibraryApp.java # Main GUI + JDBC code

---


Inside `LibraryApp.java` you have:

- MySQL connection details  
- UI components (buttons, fields, tables)  
- Functions for:
  - Adding books
  - Adding members
  - Issuing books
  - Returning books
  - Searching records
  - Updating JTable dynamically
  - SQL insert/update/delete/select queries  

---

## 🛠 Technologies Used

| Layer | Technology |
|-------|-----------|
| GUI (Frontend) | Java Swing (`JFrame`, `JTable`, `JPanel`, `JButton`) |
| Backend | Java JDBC |
| Database | MySQL |
| Date Handling | `java.time.LocalDate`, `java.sql.Date` |
| Validation | `java.util.regex.Pattern` |
| Threading | Swing Event Dispatch Thread |
| Build/Run | JDK 23 |

---

---

### 🧩 Key Features

- **Add Books** – Stores new book details into DB using INSERT query  
- **Add Members** – Saves member information (name, email, etc.)  
- **Issue a Book** – Checks availability and inserts an issue record  
- **Return a Book** – Updates `return_date` and marks book available again  
- **Search / List** – Uses JDBC SELECT queries and populates JTable dynamically  
- **Validation** – Regex-based input checking (numbers, email, ISBN, etc.)  

---

### 🧠 OOP Concepts Used

| Concept       | How It Is Used |
|---------------|----------------|
| Encapsulation | Data variables + getters/setters in components & DB functions |
| Abstraction   | Separate logical methods for DB operations, UI updates, etc. |
| Inheritance   | `LibraryApp` extends `JFrame` |
| Polymorphism  | Overriding event listeners (e.g., `actionPerformed`) |
| Modularity    | Organized methods for each operation |


---

### ⚙️ JDBC Connectivity

```java
Class.forName("com.mysql.cj.jdbc.Driver");
Connection con = DriverManager.getConnection(
    "jdbc:mysql://localhost:3306/library",
    "root",
    "yourpassword"
);
```

---
### 📤 Functional Flowchart

+---------+
| User |
+---------+
|
v
+--------------------+
| LibraryApp (UI) |
| Swing JFrame |
+--------------------+
|
v
+--------------------+
| JDBC Layer |
| DriverManager |
+--------------------+
|
v
+--------------------+
| MySQL Database |
| Books / Members |
| Issue Records |
+--------------------+
|
v
+-------------+
| Updated UI |
+-------------+

---

### 🚀 How to Run

1. Install **MySQL** and create the required tables.
2. Download & add **MySQL Connector/J** to Referenced Libraries.
3. Open the project in **VS Code** or **IntelliJ**.
4. Compile & run the project:

```bash
javac LibraryApp.java
java LibraryApp
```

---

### 📄 Included

- ✔ Complete LibraryApp.java  
- ✔ Swing UI code  
- ✔ MySQL integration  
- ✔ JDBC CRUD operations  
- ✔ JavaSE-23 runtime environment  
- ✔ VS Code project structure  

---

### 🔌 Database Requirements


Create a MySQL database with the following structure:

```sql
CREATE DATABASE IF NOT EXISTS library;
USE library;

CREATE TABLE books (
    id INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(100),
    author VARCHAR(100),
    isbn VARCHAR(50),
    added_date DATE
);

CREATE TABLE members (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    email VARCHAR(100)
);

CREATE TABLE issue_records (
    id INT PRIMARY KEY AUTO_INCREMENT,
    member_id INT,
    book_id INT,
    issue_date DATE,
    return_date DATE,
    FOREIGN KEY(member_id) REFERENCES members(id),
    FOREIGN KEY(book_id) REFERENCES books(id)
);
