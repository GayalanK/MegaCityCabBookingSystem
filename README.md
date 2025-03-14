# 🚖 MegaCity Cab Booking System

## 📌 Project Overview
The **MegaCity Cab Booking System** is a web-based platform that allows customers to book cabs online, track their bookings, and download reports. Built using **Java Servlets, JSP, and MySQL**, the system supports **customer authentication, booking management, and admin features**.

---

## 🔹 Features

### **Customer Features**
- ✅ User Registration & Login (Session-based authentication)
- ✅ Book a cab by selecting pickup/drop locations
- ✅ View booking history and download booking reports (CSV format)
- ✅ Logout with session timeout after 2 minutes of inactivity

### **Admin Features**
- ✅ Manage users and cab bookings
- ✅ Generate reports for a selected date range
- ✅ Dashboard with booking statistics

---

## 🛠️ Tech Stack

| Technology | Description |
|------------|------------|
| **Java Servlets & JSP** | Backend logic & dynamic web pages |
| **MySQL** | Database for storing user and booking details |
| **HTML, CSS, Bootstrap** | Frontend UI for a responsive design |
| **Apache Tomcat** | Web server for deployment |
| **JDBC** | Database connectivity |

---

## 📂 Project Structure
MegaCityCabBookingSystem/<br>
│── src/<br>
│   ├── com.megacitycab/<br>
│   │   ├── BookingServlet.java<br>
│   │   ├── LoginServlet.java<br>
│   │   ├── RegisterServlet.java<br>
│   │   ├── BookingReportServlet.java<br>
│   │   ├── DatabaseConnection.java<br>
│── webapp/<br>
│   ├── index.jsp<br>
│   ├── login.jsp<br>
│   ├── register.jsp<br>
│   ├── dashboard.jsp<br>
│   ├── booking.jsp<br>
│── database/<br>
│   ├── megacitycab.sql<br>
│── README.md<br>
│── .gitignore<br>
│── pom.xml (if using Maven)<br>

## 💾 Database Schema

### **`users` Table**

| Column     | Type           | Description              |
|------------|---------------|--------------------------|
| `userID`   | INT (Primary Key) | Unique ID for the user  |
| `username` | VARCHAR(50)    | Customer's name         |
| `email`    | VARCHAR(100)   | Customer's email        |
| `password` | VARCHAR(255)   | Encrypted password      |
| `role`     | VARCHAR(10)    | Either "customer" or "admin" |

### **`bookings` Table**

| Column          | Type             | Description            |
|----------------|-----------------|------------------------|
| `bookingID`    | INT (Primary Key) | Unique booking ID     |
| `userID`       | INT (Foreign Key) | Reference to `users.userID` |
| `pickupLocation` | VARCHAR(255)    | Start location        |
| `dropLocation`  | VARCHAR(255)    | Destination           |
| `carType`      | VARCHAR(50)     | Type of car booked    |
| `status`       | VARCHAR(20)     | Booking status (Pending/Completed) |
| `date`         | TIMESTAMP       | Booking date          |

---

## 📜 How to Run the Project Locally

### **🔹 Prerequisites**
1️⃣ Install **JDK 8+**  
2️⃣ Install **Apache Tomcat 9+**  
3️⃣ Install **MySQL Server**  
4️⃣ Install **Git** (if not installed)

### **🔹 Steps to Setup**
#### 1️⃣ Clone the Repository:

git clone https://github.com/GayalanK/MegaCityCabBookingSystem
<br>
**2️⃣ Import Database:**
Open MySQL Workbench or phpMyAdmin
Create a new database:

CREATE DATABASE megacitycab;
Import the megacitycab.sql file
<br>

**3️⃣ Configure Database in DatabaseConnection.java**

private static final String URL = "jdbc:mysql://localhost:3306/megacitycab"; <br>
private static final String USER = "root";  // Change if necessary <br>
private static final String PASSWORD = "";  // Change if necessary <br>

**4️⃣ Deploy to Tomcat:**

Copy the project to webapps/ in Tomcat
Start Tomcat and open http://localhost:8080/MegaCityCabBookingSystem

**📢 Contributors** <br>
👨‍💻 GayalanK – GitHub <br>

🔥 Feel free to fork and contribute!

**📜 License** <br>
This project is licensed under the MIT License.
