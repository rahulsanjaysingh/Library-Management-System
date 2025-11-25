📚 Library Management System (Java Swing + JDBC + MySQL)

A desktop-based Library Management System built using Java Swing, JDBC, and MySQL.
This project demonstrates GUI-based CRUD operations, JDBC connectivity, SQL queries, and clean modular code structure.

Designed for academic submission and portfolio demonstration with focus on Java OOP, UI design, and database handling.

✅ Features
🎯 Core Functionalities

Add new books

Update book details

Delete books

Search books

View complete list of books

Mark a book as issued / not issued

🏗 Architectural Concepts Used

Java Swing GUI (JFrame, JPanel, JTable, JTextField, etc.)

JDBC (DriverManager, PreparedStatement, ResultSet)

DAO Pattern (separate database access layer)

MVC-inspired structure (Model → DAO → UI)

OOP Concepts

Encapsulation (Book model)

Abstraction (DAO layer)

Modular class design

📂 Project Structure
LibraryManagementSystem/
├── src/
│   ├── LibraryApp.java        # Main Swing UI (JFrame)
│   ├── BookDAO.java           # Data Access Layer (CRUD operations)
│   ├── DBUtil.java            # MySQL connection helper
│   ├── Book.java              # Book model (POJO)
│
├── LibraryApp.class
├── Main.class (if generated)
│
├── Referenced Libraries/
│   └── mysql-connector-j.jar  # Required JDBC driver
│
└── JRE System Library [JavaSE-23]

🖼 UI Preview

Your uploaded screenshot is stored at:

/mnt/data/bfdaea36-4d08-4eda-af95-9ecbd550401a.png

You can embed it in GitHub like this:

![UI Screenshot](bfdaea36-4d08-4eda-af95-9ecbd550401a.png)

🛠 Technologies Used
Layer	Technology
Frontend / UI	Java Swing
Database	MySQL
Backend Connectivity	JDBC
Architecture	DAO + Modular Classes
Language	Java SE 23
🗄 Database Setup

Run these SQL commands:

CREATE DATABASE IF NOT EXISTS library;

USE library;

CREATE TABLE books (
    id INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(100) NOT NULL,
    author VARCHAR(100) NOT NULL,
    isbn VARCHAR(30),
    issued BOOLEAN DEFAULT FALSE
);

🔌 JDBC Configuration

Update credentials inside DBUtil.java:

private static final String URL  = "jdbc:mysql://localhost:3306/library";
private static final String USER = "root";
private static final String PASS = "yourpassword";


Also make sure MySQL Connector/J is added to your project.

🧩 How It Works — Flowchart
+------------------+
|     User         |
+------------------+
          |
          v
+------------------------+
| LibraryApp (Swing UI) |
+------------------------+
          |
          v
+------------------------+
| BookDAO (DB Layer)     |
+------------------------+
          |
          v
+------------------------+
|   JDBC Driver          |
+------------------------+
          |
          v
+------------------------+
|    MySQL Database      |
+------------------------+

💡 OOP Concepts Used
✔ Encapsulation

Book.java contains private fields with getters/setters.

✔ Abstraction

BookDAO hides SQL complexity from UI.

✔ Polymorphism

Can extend components (e.g., JFrame, JTable) for custom behavior.

✔ Modular Design

Each class handles one responsibility.

▶️ How to Run

Install JDK (17+ recommended)

Install MySQL

Import project in VS Code / IntelliJ / Eclipse

Add MySQL Connector/J JAR

Update credentials in DBUtil.java

Run:

java LibraryApp

📦 Project Files Included

Full GUI source code

DAO + Model classes

Database SQL script

Screenshot of application UI

README.md (this file)
