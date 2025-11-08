# 🛡️ Secure Notes App

A **Flask-based web application** that enables users to **register**, **log in**, and **manage their secure notes** securely.  
It includes user authentication, password hashing, and a modern responsive Bootstrap interface.

## 🧭 Overview

**Secure Notes App** allows users to create an account, log in, and manage their personal notes in a secure environment.  
It ensures:
- Encrypted password storage using **Werkzeug security**
- User authentication via **Flask-Login**
- Clean and responsive design with **Bootstrap 5**

---

## 🏗️ Project Structure
```
Secure_Notes_App/
│
├── app.py # Main Flask application
├── forms.py # Form classes (Register & Login)
│
├── instance/
│ └── notes.db # SQLite database (auto-generated)
│
├── static/
│ └── css/
│ └── custom.css # Optional custom CSS styling
│
├── templates/
│ ├── base.html # Common layout (Bootstrap Navbar)
│ ├── login.html # Login page
│ ├── register.html # Registration page
│ └── notes.html # Notes dashboard (protected route)
│
├── .venv/ # Virtual environment
└── README.md # Project documentation

```
---

## ⚙️ Technologies Used

| Library | Purpose |
|----------|----------|
| **Flask** | Core web framework |
| **Flask-SQLAlchemy** | ORM for managing the database |
| **Flask-Login** | Authentication and session management |
| **Flask-WTF** | Secure form handling |
| **Werkzeug Security** | Password hashing and verification |
| **Bootstrap 5** | Front-end framework for styling |
| **SQLite** | Lightweight local database |

---

## 🧩 Installation Guide

###  Clone the Repository
git clone https://github.com/yourusername/Secure_Notes_App.git
cd Secure_Notes_App

### Install Dependencies
pip install flask flask_sqlalchemy flask_login flask_wtf werkzeug

### Run the App
python app.py


### Then open your browser and go to:
👉 http://127.0.0.1:5000

###🧠 How It Works

🔐 1. User Registration

Users can sign up via /register.

Passwords are hashed using generate_password_hash() before being stored.

🔑 2. Login

Users log in through /login.

Flask-Login manages sessions and redirects unauthorized users.

🗒️ 3. Secure Notes

Only logged-in users can access /notes.

This page displays user-specific data (to be expanded later).

🚪 4. Logout

The /logout route ends the session safely.

```
## 🧱 Database Schema

| **Field**        | **Type**        | **Description**           |
|------------------|-----------------|----------------------------|
| `id`             | Integer          | Primary key                |
| `username`       | String(150)      | Unique username            |
| `password_hash`  | String(200)      | Encrypted (hashed) password |

---

### 🗒️ Note Model *(Optional Future Feature)*

| **Field**   | **Type**      | **Description**            |
|--------------|---------------|-----------------------------|
| `id`         | Integer       | Primary key                 |
| `user_id`    | Foreign Key   | Associated user ID          |
| `content`    | Text          | User’s note content         |
```

🎨 Front-End Design
- Designed with Bootstrap 5 via CDN.
- Shared layout handled by base.html.
- Each page (login, register, notes) extends the base layout.
- Includes flash message support for success/error notifications.

🌐 Routes Summary
Route	Method(s)	Description
/	GET	Home route
/register	GET, POST	Register a new user
/login	GET, POST	User login
/logout	GET	Log out current user
/notes	GET	Protected notes page
