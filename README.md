# SafeHer – Women's Safety, Dignity & Freedom in Public Spaces

SafeHer is a modern, responsive, and secure web application designed to improve women's safety in public spaces. This repository contains both a high-fidelity interactive frontend prototype (ideal for standalone demonstration) and a secure PHP/MySQL backend architecture implementing cybersecurity best practices.

---

##  Key Features

* **Emergency SOS Dispatch**: One-tap panic button triggers instant coordinates mapping and mocks SMS dispatch logs to trusted contacts/guardians.
* **Interactive Safety Mapping**: Displays safe, moderate, and high-risk zones in **Mehsana, Gujarat** using colored transparent circles. Search locations and toggle nearby police stations and hospitals.
* **Secure Incident Reporting**: Forms to submit incidents (e.g. Unwanted Staring) with options for file evidence upload, anonymous submittals, and admin review flags.
* **Trusted Guardian Configuration**: Manage (Add/Edit/Delete) emergency contacts and nominate guardians to receive automatic SMS alerts.
* **Dual Dashboards**:
  * **User Dashboard**: Real-time stats, bulletin boards, contacts directory, custom profiles, and incident logs.
  * **Admin Control Center**: Analytics charts (Chart.js), report verification queues, risk area coordinate configurations, and notification broadcasting.

---

##  Cybersecurity Implementations

To ensure data integrity, privacy, and protection against web vulnerabilities, SafeHer implements:
1. **Prepared SQL Statements (PDO)**: Complete protection against SQL Injection attacks.
2. **Input Sanitization & Output Escaping**: Prevents Cross-Site Scripting (XSS) injection.
3. **Secure Password Hashing**: Passwords stored using `PASSWORD_DEFAULT` (bcrypt).
4. **Session Security & Fixation Protection**: Regulates session identifiers on authorization events (`session_regenerate_id(true)`) and validates HTTP User Agent states.
5. **Secure HTTP Headers**: Configured headers for Content Security Policy (CSP), X-Frame-Options (Clickjacking protection), and X-Content-Type-Options.
6. **Cross-Site Request Forgery (CSRF) Tokens**: Form authentication verified via randomized tokens.

---

##  Project Folder Structure

```
safeher/
├── index.html              # Landing Portal & Login Modals
├── dashboard.html          # User Control Dashboard
├── admin.html              # Admin System Control Panel
├── css/
│   └── styles.css          # Premium Design System CSS
├── js/
│   └── app.js              # Core Client Scripts & Map Overrides
├── backend/
│   ├── database.sql        # MySQL Database Schema Script
│   ├── config.php          # Database Configuration & Headers
│   ├── register.php        # User Signup Handler
│   ├── login.php           # Secure Login Authentication
│   ├── otp_verify.php      # OTP validation
│   ├── report_incident.php # File Upload & Incident submission
│   ├── emergency_sos.php   # SOS alerts and phone dispatcher
│   ├── get_data.php        # Unified data feed API
│   ├── admin_actions.php   # Admin control panel endpoints
│   └── logout.php          # Secure session clearance script
└── README.md               # Setup Guide and Features
```

---

##  Installation & Setup

SafeHer is built as a hybrid application. You can run the **interactive frontend prototype immediately** by double-clicking `index.html` in any browser. To connect the database and run the full PHP backend:

### Prerequisites
* Web Server: Apache (with PHP 8.0+)
* Database: MySQL / MariaDB
* Recommended Stack: XAMPP, WAMP, or MAMP.

### Server Deployment Steps
1. **Copy Files**: Clone or extract the project directory into your web server's root folder (e.g., `C:/xampp/htdocs/safeher/`).
2. **Database Setup**:
   * Open phpMyAdmin (`http://localhost/phpmyadmin/`).
   * Create a new database named `safeher_db`.
   * Import the `backend/database.sql` file to create tables and seed default records.
3. **Configuration**:
   * Open `backend/config.php` and verify the MySQL credentials (`DB_USER`, `DB_PASS`, `DB_NAME`).
4. **Run Application**:
   * Open your browser and navigate to `http://localhost/safeher/index.html`.

### Default Demo Credentials
* **Sample User Profile**:
  * Identity: `maitri.chauhan@gmail.com` (or mobile: `+91 9876543210`)
  * Password: `password123`
  * Default Location: `Mehsana, Gujarat`
* **Sample Admin Profile**:
  * Identity: `admin@safeher.in`
  * Password: `password123`
