# Hardware Repair Request Tracker

> A role-based web application for managing hardware repair requests, technician workflows, and administrative oversight in a single unified system.

![Status](https://img.shields.io/badge/Status-In%20Development-yellow)
![PHP](https://img.shields.io/badge/PHP-7.4%2B-blue)
![MySQL](https://img.shields.io/badge/MySQL-8.0-orange)
![Apache](https://img.shields.io/badge/Server-Apache-red)

---

<a id="overview"></a>
## 📖 Overview

The **Hardware Repair Request Tracker** is a web-based system designed to streamline the process of submitting, tracking, assigning, and managing hardware repair requests.

This system is ideal for:
- University IT departments
- Organizations with internal hardware support teams
- Small-to-medium service centers

It provides **three dedicated dashboards** (Customer, Technician, Admin), ensuring that each user role has access only to the features relevant to them.  
From request creation to repair completion and payment tracking, the entire workflow is handled transparently and efficiently.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [System Workflow](#system-workflow)
- [Screenshots](#screenshots)
- [User Roles](#user-roles)
- [Technologies Used](#technologies-used)
- [Database Design](#database-design)
   - [Database Setup](#database-setup)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Security & Access Control](#security--access-control)
- [Team](#team)
- [License](#license)

---

<a id="features"></a>
## ✨ Features

### 🔧 Repair Request Management
- Create new hardware repair requests
- Track request status in real-time
- View request history and updates
- Support for multiple device types (Laptop, Phone, etc.)

### 👨‍🔧 Technician Workflow
- View approved repair requests
- Send repair proposals to customers
- Manage accepted appointments
- Update request states (Assigned, Completed, Returned, Cannot Fix)
- Track sent proposals and their status
- Submit repair completion details

### 🧑‍💼 Administrative Control
- Approve or reject user registrations
- Manage users and assign roles
- Monitor system-wide activity
- Track completed repairs and payments
- View reports and feedback

### 💳 Payment & Completion Tracking
- Record completed repairs
- Track payment status (Cash-based)
- Maintain repair and payment history

### 🔐 Authentication & Authorization
- Secure login & registration system
- Role-based access control
- Admin approval for new users

---

<a id="system-workflow"></a>
## 🔄 System Workflow

1. **User Registration**
   - Customers and technicians register through the system
   - Admin approves registrations before access is granted

2. **Request Creation**
   - Customers submit hardware repair requests
   - Requests are stored with status `Pending`

3. **Proposal & Assignment**
   - Technicians can view approved requests
   - Technicians send repair proposals to customers
   - Customers accept proposals
   - Appointments are scheduled

4. **Repair Process**
   - Technician works on accepted appointments
   - Technician updates progress
   - Repair outcomes are recorded

5. **Completion**
   - Repair marked as `Completed` or `Returned`
   - Payment details recorded

6. **Monitoring**
   - Admin monitors activity, users, feedback, and reports

---

<a id="screenshots"></a>
## 📸 Screenshots

### 🏠 Home / Landing Page
![Home Page](https://github.com/user-attachments/assets/c11a2eb2-0ead-499c-a353-651b9cb8bb44)


---

### 👤 Customer Dashboard
![Customer Dashboard](https://github.com/user-attachments/assets/603852df-64d5-4725-b3ac-38a022c72370)

---

### 👨‍🔧 Technician Dashboard
![Technician Dashboard](https://github.com/user-attachments/assets/f67eadb1-3fb3-4c18-9ce0-0f6897424e43)

---

### 🧑‍💼 Admin Dashboard
![Admin Dashboard](https://github.com/user-attachments/assets/30055c16-c82e-4f5b-9458-75a815416ff1)


---

<a id="user-roles"></a>
## 👥 User Roles

### 1️⃣ Admin
- Approve pending user registrations
- Manage users and roles
- View system-wide statistics
- Monitor requests, payments, and feedback
- Generate reports

### 2️⃣ Technician
- View assigned repair requests
- Update repair status
- Manage appointments
- Mark work as completed or returned

### 3️⃣ Customer
- Submit repair requests
- View and accept technician proposals
- Track request status
- View request history and completed repairs
- Manage profile information
- Receive updates from technicians

---

<a id="technologies-used"></a>
## 🛠️ Technologies Used

### Backend
- **PHP 7.4+**
- Procedural PHP architecture
- Session-based authentication

### Frontend
- **HTML5**
- **CSS3**
- **JavaScript**
- Responsive dashboard layout

### Database
- **MySQL 8.0**
- Relational database design

### Server Environment
- **Apache**
- **XAMPP / WAMP**

---

<a id="database-design"></a>
## 🗄️ Database Design

Main tables used in the system:

1. `users`  
   - Stores user details and roles (Admin, Technician, Customer)

2. `requests`  
   - Stores hardware repair requests and their statuses

3. `appointments`  
   - Technician appointment scheduling

4. `payments`  
   - Tracks payment status for completed repairs

5. `feedback`  
   - Stores user feedback for admin review

<a id="database-setup"></a>
### Database Setup

#### Option 1: Using phpMyAdmin (Recommended)
1. Open phpMyAdmin in your browser: `http://localhost/phpmyadmin`
2. Click on "New" to create a new database
3. Enter database name: `hardware_repair_tracker`
4. Select collation: `utf8mb4_general_ci`
5. Click "Create"
6. Select the newly created database
7. Click on "Import" tab
8. Choose file: Browse to `sql/database.sql`
9. Click "Go" to import

#### Option 2: Using MySQL Command Line
```bash
# Login to MySQL
mysql -u root -p

# Create database
CREATE DATABASE hardware_repair_tracker;

# Exit MySQL
exit;

# Import SQL file
mysql -u root -p hardware_repair_tracker < sql/database.sql
```

<a id="installation"></a>
## 🚀 Installation

### Prerequisites
- **XAMPP** or **WAMP** installed on your system
- **Apache** and **MySQL** services running
- **PHP 7.4+** enabled

### Step-by-Step Installation

#### 1️⃣ Clone or Download the Repository
```bash
git clone https://github.com/your-username/hardware-repair-request-tracker.git
```
Or download the ZIP file and extract it.

#### 2️⃣ Move Project to Server Directory

Copy the `Hardware` folder to your server root directory:
- **XAMPP**: `C:\xampp\htdocs\Hardware`
- **WAMP**: `C:\wamp\www\Hardware`
- **Linux/Mac XAMPP**: `/opt/lampp/htdocs/Hardware`

#### 3️⃣ Create and Import Database

Follow the [Database Setup](#database-setup) instructions above to:
1. Create a database named `hardware_repair_tracker`
2. Import the `sql/database.sql` file

#### 4️⃣ Configure Database Connection

Open the `db.php` file in the root directory and update the database credentials:

```php
<?php
$servername = "localhost";
$username = "root";           // Your MySQL username
$password = "";               // Your MySQL password (empty for XAMPP default)
$dbname = "hardware_repair_tracker";

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);

// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
?>
```

#### 5️⃣ Start Apache and MySQL

Make sure both services are running:
- Open XAMPP/WAMP Control Panel
- Start **Apache** module
- Start **MySQL** module

#### 6️⃣ Access the Application

Open your web browser and navigate to:
```
http://localhost/Hardware
```

#### 7️⃣ Default Login (Admin Account)

After importing the database, you can login with:
- **Username**: `admin` (check your database for actual credentials)
- **Password**: Set in your database

> **Note**: Make sure to change default credentials after first login for security.

---

<a id="project-structure"></a>
## 📁 Project Structure
```
Hardware/
├── admin/                     # Admin dashboard & controls
│   ├── feedback.php           # View user feedback
│   ├── index.php              # Admin dashboard
│   ├── payments.php           # Payment management
│   ├── reports.php            # System reports
│   ├── requests.php           # Manage repair requests
│   ├── users_manage.php       # User management
│   └── users_pending.php      # Approve pending users
├── assets/                    # Static resources
│   ├── css/
│   │   └── style.css          # Main stylesheet
│   └── js/
│       └── app.js             # JavaScript functionality
├── auth/                      # Authentication module
│   ├── choose_role.php        # Role selection
│   ├── login.php              # User login
│   ├── logout.php             # User logout
│   ├── register_customer.php # Customer registration
│   └── register_technician.php # Technician registration
├── customer/                  # Customer dashboard
│   ├── completed.php          # View completed repairs
│   ├── index.php              # Customer dashboard
│   ├── my_requests.php        # View my requests
│   ├── profile.php            # Customer profile
│   ├── proposals.php          # View proposals
│   └── request_new.php        # Create new request
├── partials/                  # Reusable components
│   ├── footer.php             # Page footer
│   ├── header.php             # Page header
│   └── nav.php                # Navigation bar
├── sql/                       # Database scripts
│   └── database.sql           # Database schema
├── technician/                # Technician dashboard
│   ├── accepted_appointments.php # Manage appointments
│   ├── approved_requests.php  # View approved requests
│   ├── completed.php          # View completed work
│   ├── index.php              # Technician dashboard
│   ├── profile.php            # Technician profile
│   └── proposals_sent.php     # View sent proposals
├── config.php                 # Configuration settings
├── db.php                     # Database connection
├── features.php               # Features page
├── help.php                   # Help & support page
├── index.php                  # Landing page
└── README.md                  # Project documentation
```

---

<a id="security--access-control"></a>
## 🔐 Security & Access Control

- Session-based authentication
- Role-based dashboard access
- Admin approval for new registrations
- Restricted page access per role

---

<a id="team"></a>
## 🤝 Team

- **[Your Name]** – Full Stack Development
- **[Team Member]** – Database & Backend
- **[Team Member]** – UI/UX & Testing

---

<a id="license"></a>
## 📄 License

This project is licensed under the MIT License.
You are free to use, modify, and distribute this project with proper attribution.

