================================================================================
        HOSPITAL MANAGEMENT SYSTEM (HMS)
        A Web-Based Platform for Connecting Patients with Healthcare Services
        in Real-Time
================================================================================

  Final Year Project (FYP)
  Student      : Muhammad Hamza
  Roll No      : F22BINFT1M01169
  Supervisor   : Ms. Kainat
  Department   : Information Technology — Faculty of Computing
  University   : The Islamia University of Bahawalpur

================================================================================
  TABLE OF CONTENTS
================================================================================

  1. Project Overview
  2. Problem Statement
  3. Key Features
  4. Tech Stack
  5. System Architecture
  6. Database Schema (Summary)
  7. User Roles & Access
  8. Installation & Setup
  9. Project Structure
  10. Screenshots / UI Overview
  11. Project Timeline
  12. Future Enhancements
  13. Contributors
  14. License

================================================================================
  1. PROJECT OVERVIEW
================================================================================

The Hospital Management System (HMS) is a fully web-based application designed
to digitalize and streamline hospital operations. It serves as a centralized
platform where patients, doctors, and administrators interact in real time to
manage appointments, medical records, billing, and hospital resources.

The system aims to:
  - Eliminate manual paperwork and reduce administrative overhead
  - Enable patients to register, book appointments, and access medical history
  - Give doctors and staff a unified dashboard for managing healthcare delivery
  - Provide administrators with full control over hospital operations and reports
  - Integrate AI chatbot support and location-based hospital matching

This project was developed as part of the Final Year Project requirement for the
Bachelor of Information Technology degree at The Islamia University of Bahawalpur.

================================================================================
  2. PROBLEM STATEMENT
================================================================================

Traditional hospital systems rely on manual records, outdated directories, and
paper-based processes that cause significant delays — especially in emergencies.
Patients struggle to find nearby hospitals, book appointments quickly, or access
their medical history. Hospitals face challenges managing patient flow and
coordinating staff and services efficiently.

HMS directly addresses these issues by providing a real-time, automated,
role-based digital platform for seamless patient-hospital communication.

================================================================================
  3. KEY FEATURES
================================================================================

  [PATIENT FEATURES]
  ------------------
  >> Patient Registration & Authentication
     - Secure sign-up and login with role-based access
     - Personal profile with medical history, location, and records

  >> Appointment Booking
     - Browse available doctors by specialization and time slot
     - Real-time appointment scheduling with confirmation

  >> Medical History Access
     - View past diagnoses, prescriptions, and lab results
     - Download or print medical reports

  >> Hospital & Service Finder
     - Geolocation-based nearby hospital search
     - Map integration for directions to healthcare centers
     - Service-matching based on medical need and proximity

  >> Emergency Numbers Directory
     - City-wise searchable directory of emergency contacts
     - Ambulance services, hospital hotlines, and clinics

  >> AI Info Chatbot
     - Answers FAQs about services, appointment steps, and health tips

  [DOCTOR FEATURES]
  -----------------
  >> Doctor Dashboard
     - View and manage assigned patient appointments
     - Access and update patient medical records

  >> Prescription Management
     - Issue digital prescriptions linked to patient profiles

  [ADMIN FEATURES]
  ----------------
  >> Full System Control
     - Manage doctors, patients, staff, and departments
     - Monitor hospital-wide appointments and billing records

  >> Billing & Invoicing
     - Auto-generate bills for consultations, treatments, and medicines
     - Track payment status per patient

  >> Reports & Analytics
     - Generate patient, appointment, and financial reports
     - Search and filter records across the system

  >> Pharmacy / Inventory (Optional Module)
     - Track medicine stock and availability

================================================================================
  4. TECH STACK
================================================================================

  Layer           Technology
  -----------     -----------------------------------------------------------
  Frontend        HTML5, CSS3, JavaScript, jQuery, AJAX, Bootstrap (optional)
  Backend         PHP (5.6 / 7.x / 8.x)  |  Alternative: Node.js / Django
  Database        MySQL 5.x / 8.x         |  Alternative: MongoDB / PostgreSQL
  Server          XAMPP / WAMP / MAMP / LAMP
  Hosting         AWS / Azure / GitHub Pages
  Security        SSL Encryption, Secure Authentication, Role-Based Access
  UI Design       Figma / Canva (Wireframes & Prototypes)
  Browser Support Chrome, Firefox, Opera, Internet Explorer

================================================================================
  5. SYSTEM ARCHITECTURE
================================================================================

  Pattern: MVC (Model - View - Controller)
  -----------------------------------------

  MODEL       →   Handles all database interactions and business logic
  VIEW        →   Presents data to users via HTML/CSS/JavaScript interfaces
  CONTROLLER  →   Processes user requests and coordinates Model ↔ View

  Controllers:
  ------------
  Admin Controller       →   Users, doctors, departments, system settings
  Doctor Controller      →   Doctor profiles, appointments, prescriptions
  Patient Controller     →   Registration, appointments, medical history
  Appointment Controller →   Scheduling, slot management, status updates
  Billing Controller     →   Invoices, payments, billing records

  UML Diagrams Included:
  ----------------------
  - Use Case Diagram     (system functionality from user perspective)
  - Class Diagram        (static structure: Patient, Doctor, Appointment, Admin)
  - Sequence Diagram     (appointment booking interaction flow)
  - ER Diagram           (entity relationships in the database)

================================================================================
  6. DATABASE SCHEMA (SUMMARY)
================================================================================

  TABLE: patients
  ---------------
  patient_id (PK), name, age, gender, contact, address

  TABLE: doctors
  --------------
  doctor_id (PK), name, specialization, contact, availability

  TABLE: appointments
  -------------------
  appointment_id (PK), patient_id (FK), doctor_id (FK), date, time, status

  TABLE: billing
  --------------
  bill_id (PK), patient_id (FK), amount, payment_status, bill_date

  TABLE: users (Authentication)
  -----------------------------
  user_id (PK), username, password (hashed), role [admin / doctor / patient]

  Relationships:
  --------------
  - One Patient  → Many Appointments
  - One Doctor   → Many Appointments
  - Each Appointment → Linked to ONE patient and ONE doctor
  - Each Bill    → Linked to ONE patient

================================================================================
  7. USER ROLES & ACCESS
================================================================================

  Role          Access Level
  ----------    ---------------------------------------------------------------
  Admin         Full system access — users, reports, billing, departments
  Doctor        Patient records, appointments, prescriptions
  Patient       Own profile, appointments, medical history, billing
  Staff         Limited operational access (if configured)

================================================================================
  8. INSTALLATION & SETUP
================================================================================

  PREREQUISITES:
  --------------
  - PHP >= 7.x installed
  - MySQL >= 5.x installed
  - XAMPP / WAMP / LAMP running
  - Web browser (Chrome or Firefox recommended)

  STEPS:
  ------

  Step 1 — Clone or Download the Project
  ---------------------------------------
  > git clone https://github.com/your-username/hospital-management-system.git
  OR download and extract the ZIP file.

  Step 2 — Move to Server Directory
  ----------------------------------
  > Place the project folder inside:
    - XAMPP:  C:/xampp/htdocs/
    - WAMP:   C:/wamp64/www/

  Step 3 — Create the Database
  -----------------------------
  > Open phpMyAdmin (http://localhost/phpmyadmin)
  > Create a new database: e.g., hms_db
  > Import the SQL file:
    File → database/hms_db.sql → Click Import

  Step 4 — Configure Database Connection
  ----------------------------------------
  > Open:  config/db.php  (or similar config file)
  > Update the following:

      $host     = "localhost";
      $username = "root";
      $password = "";          // your MySQL password
      $database = "hms_db";

  Step 5 — Run the Application
  -----------------------------
  > Start Apache and MySQL in XAMPP/WAMP
  > Open browser and visit:
    http://localhost/hospital-management-system/

  Step 6 — Default Login Credentials
  ------------------------------------
  > Admin Login:
      Username : admin
      Password : admin123

  (Change credentials after first login for security)

================================================================================
  9. PROJECT STRUCTURE
================================================================================

  hospital-management-system/
  │
  ├── config/
  │   └── db.php                  # Database connection settings
  │
  ├── controllers/
  │   ├── AdminController.php
  │   ├── DoctorController.php
  │   ├── PatientController.php
  │   ├── AppointmentController.php
  │   └── BillingController.php
  │
  ├── models/
  │   ├── Patient.php
  │   ├── Doctor.php
  │   ├── Appointment.php
  │   └── Billing.php
  │
  ├── views/
  │   ├── home/
  │   ├── admin/
  │   ├── doctor/
  │   ├── patient/
  │   └── auth/
  │
  ├── assets/
  │   ├── css/
  │   ├── js/
  │   └── images/
  │
  ├── database/
  │   └── hms_db.sql              # SQL dump for database setup
  │
  ├── docs/
  │   ├── SRS_Final_Year_Project.docx
  │   ├── SDD_Template.docx
  │   └── Project_Proposal.docx
  │
  └── README.txt                  # This file

================================================================================
  10. SCREENSHOTS / UI OVERVIEW
================================================================================

  Screen                  Description
  --------------------    -------------------------------------------------------
  Home Page               Hospital info, navigation, Book Appointment button
  Login Page              Username + Password fields with role-based redirect
  Admin Dashboard         Manage doctors, patients, departments, view reports
  Doctor Dashboard        View appointments, manage patient records
  Patient Dashboard       Book appointment, view medical history and bills
  Appointment Form        Select doctor, date, time slot and confirm booking
  Billing Page            Invoice view with payment status per patient
  Emergency Directory     City-wise emergency contacts, searchable by region

  Design Theme:
  -------------
  - Primary Color   : Teal / Green  (healthcare, trust, freshness)
  - Secondary Color : White         (clarity, cleanliness)
  - Accent          : Light Gray    (borders, secondary sections)
  - Typography      : Sans-serif (Arial / Open Sans / Roboto)
  - Philosophy      : Flat, minimal, professional medical UI

================================================================================
  11. PROJECT TIMELINE
================================================================================

  Month     Milestone
  --------  -------------------------------------------------------------------
  Month 1   Requirement analysis, stakeholder planning, SRS documentation
  Month 2   UI/UX wireframes, database schema design, SDD documentation
  Month 3   Frontend development (HTML, CSS, JS, Bootstrap)
  Month 4   Backend development (PHP, MySQL, MVC integration)
  Month 5   Testing — Unit, Integration, and User Acceptance Testing (UAT)
  Month 6   Deployment, final documentation, and FYP submission

  Development Methodology: Agile (iterative sprints with continuous testing)

================================================================================
  12. FUTURE ENHANCEMENTS
================================================================================

  [Short-Term]
  >> SMS / Email appointment reminders for patients and doctors
  >> Mobile-responsive PWA (Progressive Web App) version
  >> Enhanced pharmacy and inventory management module

  [Long-Term]
  >> Mobile App (Android & iOS) for patients and doctors
  >> IoT-based real-time patient monitoring integration
  >> AI-based disease prediction and health risk assessment
  >> Cloud-based Electronic Medical Record (EMR) sharing
  >> Multi-hospital support and inter-hospital patient transfer
  >> Telemedicine / video consultation module

================================================================================
  13. CONTRIBUTORS
================================================================================

  Name              : Muhammad Hamza
  Roll No           : F22BINFT1M01169
  Department        : Information Technology
  Faculty           : Faculty of Computing
  University        : The Islamia University of Bahawalpur
  Supervisor        : Ms. Kainat
  Project Type      : Final Year Project (FYP)

================================================================================
  14. LICENSE
================================================================================

  This project is developed for academic purposes as part of the Final Year
  Project requirement at The Islamia University of Bahawalpur. All rights
  belong to the student and institution. Unauthorized commercial use is
  not permitted without prior written consent.

================================================================================
  "Transforming Healthcare Delivery — One Line of Code at a Time."
================================================================================
