
<div align="center">

# Parking Reservation

### Reservation & Management Platform

A full-stack web application designed to simplify parking reservations and management through online bookings, parking slot availability, digital payments, QR-based vehicle entry and exit, and administrative controls.

<br />

<a href="https://smart-parking-reservation-system-one.vercel.app/">
  <img src="https://img.shields.io/badge/🚀_Live_Demo-Explore_Project-2563EB?style=for-the-badge" />
</a>

<br /><br />

<img src="https://img.shields.io/badge/Frontend-React-61DAFB?logo=react&logoColor=black" />
<img src="https://img.shields.io/badge/Backend-FastAPI-009688?logo=fastapi&logoColor=white" />
<img src="https://img.shields.io/badge/Database-PostgreSQL-4169E1?logo=postgresql&logoColor=white" />
<img src="https://img.shields.io/badge/Language-Python-3776AB?logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/Build-Vite-646CFF?logo=vite&logoColor=white" />

</div>

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Project Highlights](#-project-highlights)
- [Key Features](#-key-features)
- [Technology Stack](#-technology-stack)
- [System Architecture](#-system-architecture)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Environment Configuration](#-environment-configuration)
- [Database Information](#-database-information)
- [API Documentation](#-api-documentation)
- [Booking Workflow](#-booking-workflow)
- [Security](#-security)
- [Future Improvements](#-future-improvements)
- [Contributing](#-contributing)
- [Project Information](#-project-information)

---

## 🌟 Overview

**Parking Reservation** is a web-based reservation and management platform designed to improve the parking experience for users and simplify parking operations for administrators.

The platform allows users to discover parking areas, check available parking slots, make reservations, access booking information, and use QR-based vehicle entry and exit functionality.

Administrators can manage parking areas, parking slots, bookings, registered users, EV charging facilities, and other operational information through a centralized dashboard.

The application combines a React frontend, a FastAPI backend, and a PostgreSQL database to provide an integrated full-stack solution.

### 🎯 Project Objectives

- Simplify the parking reservation process.
- Improve parking space utilization.
- Reduce the time spent searching for available parking.
- Digitize reservation and parking management workflows.
- Provide centralized administrative controls.
- Improve the overall parking experience.

## 💡 Project Highlights

- **User Portal:** Search parking areas, check availability, and reserve parking spaces.
- **Admin Dashboard:** Manage parking areas, slots, users, bookings, and operations.
- **QR-Based Operations:** Support vehicle entry and exit verification.
- **Reservation Management:** Handle booking creation, status updates, and cancellations.
- **EV Charging Support:** Manage electric vehicle charging facilities.
- **Full-Stack Architecture:** React, FastAPI, SQLAlchemy, and PostgreSQL.

## ✨ Key Features

### 👤 User Portal

- User registration and secure login.
- Search parking areas and view available parking slots.
- Check slot availability based on date and time.
- Reserve parking slots online.
- View booking history and booking details.
- Access the digital payment module.
- Generate QR codes for parking entry.
- Access QR-based parking exit functionality.
- Navigate to assigned parking locations.
- View booking-related notifications.
- Submit, update, and delete parking feedback where permitted.

### 🛠️ Admin Dashboard

- Centralized administrative dashboard.
- Manage parking areas and parking slots.
- View and manage user bookings.
- Manage registered users.
- Monitor parking occupancy and availability.
- Manage EV charging facilities.
- Generate parking reports.
- Manage administrative settings.
- Monitor payment and refund information.
- Handle QR-based entry and exit operations.

### 🚘 Reservation & Parking Management

- Calculate parking slot availability based on existing bookings.
- Prevent overlapping reservations.
- Manage automated booking status updates.
- Support QR-based vehicle entry verification.
- Support QR-based vehicle exit verification.
- Complete bookings after exit verification.
- Release parking slots after booking completion or cancellation.
- Support EV charging facilities.
- Provide indoor parking navigation support.

> **Note:** Feature descriptions reflect the documented project functionality. External payment gateways, IoT sensors, and live integrations depend on their actual implementation and configuration.

## 💻 Technology Stack

| Component | Technologies |
|---|---|
| Frontend | React.js, Vite, JavaScript, HTML, CSS |
| Backend | Python, FastAPI |
| Database | PostgreSQL |
| ORM | SQLAlchemy |
| Authentication | JWT-based authentication |
| API Documentation | Swagger UI / OpenAPI |
| QR Code | Python qrcode, qrcode.react, html5-qrcode |
| Frontend Routing | React Router |
| Version Control | Git and GitHub |

## 🏗️ System Architecture

The application follows a client-server architecture.

The React frontend communicates with the FastAPI backend through REST APIs. The backend handles authentication, application logic, request processing, and database operations using SQLAlchemy ORM.

```mermaid
flowchart TB
    USER[User Portal]
    ADMIN[Admin Portal]

    FRONTEND[React.js + Vite Frontend]

    API[FastAPI REST API]

    AUTH[JWT Authentication]
    ROUTES[Application Routes]

    ORM[SQLAlchemy ORM]

    DATABASE[(PostgreSQL Database)]

    USER --> FRONTEND
    ADMIN --> FRONTEND

    FRONTEND <--> API

    API --> AUTH
    API --> ROUTES

    ROUTES --> ORM
    ORM <--> DATABASE
```

## 📁 Project Structure

```text
parking-reservation-platform/
│
├── backend/
│   ├── app/
│   │   ├── routes/
│   │   │   ├── admin.py
│   │   │   ├── bookings.py
│   │   │   ├── feedback.py
│   │   │   ├── navigation.py
│   │   │   ├── notifications.py
│   │   │   ├── parking.py
│   │   │   ├── payments.py
│   │   │   ├── qr.py
│   │   │   ├── search.py
│   │   │   ├── slots.py
│   │   │   └── users.py
│   │   │
│   │   ├── auth.py
│   │   ├── database.py
│   │   ├── main.py
│   │   ├── models.py
│   │   └── schemas.py
│   │
│   ├── requirements.txt
│   └── .env
│
├── frontend/
│   └── frontendSmartPark/
│       ├── public/
│       ├── src/
│       │   ├── admin/
│       │   ├── assets/
│       │   ├── components/
│       │   └── pages/
│       ├── package.json
│       └── vite.config.js
│
├── database/
│
├── .gitignore
└── README.md
```

## 🚀 Getting Started

Follow these instructions to run the application locally.

### Prerequisites

Make sure you have installed:

- Python 3.10 or later
- Node.js and npm
- PostgreSQL
- Git

### 1. Clone the Repository

```bash
git clone https://github.com/coretech001/parking-reservation-platform.git

cd parking-reservation-platform
```

### 2. Backend Setup

Navigate to the backend directory:

```bash
cd backend
```

Create a Python virtual environment:

```bash
python -m venv venv
```

Activate the virtual environment.

**Windows PowerShell:**

```powershell
.\venv\Scripts\Activate.ps1
```

**macOS / Linux:**

```bash
source venv/bin/activate
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

### 3. Environment Configuration

Create a `.env` file inside the `backend` directory.

Add the following configuration:

```env
DATABASE_URL=postgresql+psycopg2://postgres:YOUR_PASSWORD@localhost:5432/smartparking

SECRET_KEY=YOUR_SECRET_KEY
```

Replace the example values with your PostgreSQL credentials and a securely generated secret key.

**Important:** Never commit your `.env` file, database credentials, or secret keys to GitHub.

### 4. Database Setup

1. Start your PostgreSQL server.
2. Create a database named `smartparking`.
3. Configure the database credentials in your `.env` file.
4. Execute the project's database schema or initialization process to create the required tables.

### 5. Run the Backend

From the `backend` directory, execute:

```bash
python -m uvicorn app.main:app --reload
```

Backend server:

```text
http://127.0.0.1:8000
```

Swagger API documentation:

```text
http://127.0.0.1:8000/docs
```

### 6. Frontend Setup

Open a second terminal and navigate to the frontend directory from the repository root:

```bash
cd frontend/frontendSmartPark
```

Install frontend dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

The frontend is usually available at:

```text
http://localhost:5173
```

Open the URL displayed in your terminal if Vite selects a different port.

## 🗄️ Database Information

The application uses PostgreSQL for persistent data storage and SQLAlchemy as its Object Relational Mapper (ORM).

The database supports information related to:

- Users and authentication.
- Parking areas and parking slots.
- Reservations and booking statuses.
- Payments and refunds.
- EV charging facilities.
- Indoor navigation.
- QR-based parking operations.
- Notifications and feedback.

## 🔌 API Documentation

The backend provides RESTful APIs developed with FastAPI.

Interactive API documentation is available through Swagger UI when the backend is running.

**Local API Documentation:**

http://127.0.0.1:8000/docs

### API Modules

- User Management
- Parking Area Management
- Parking Slot Management
- Booking Management
- Payment Operations
- QR Code Operations
- Navigation
- Notifications
- Feedback Management
- Administration

## 🔄 Booking Workflow

The main reservation and vehicle entry/exit workflow:

```mermaid
flowchart TD
    A[Search Parking Area]
    B[View Available Slots]
    C[Select Parking Slot]
    D[Create Booking]
    E[Complete Payment]
    F[Generate Booking QR]
    G[Verify Vehicle Entry]
    H[Verify Vehicle Exit]
    I[Complete Booking]
    J[Release Parking Slot]

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
    F --> G
    G --> H
    H --> I
    I --> J
```

## 🔐 Security

The documented security features include:

- JWT-based authentication.
- Role-based access for users and administrators.
- Environment variables for sensitive configuration.
- Backend validation for booking and parking operations.
- Protection of database credentials and secret keys.

For production deployments, review authorization checks, input validation, password hashing, CORS configuration, secret management, and payment security.

## 🚀 Future Improvements

Potential enhancements for future versions:

- Integration with real-time IoT parking sensors.
- Live parking occupancy monitoring.
- GPS-based navigation to parking locations.
- Additional payment gateway integrations.
- Mobile application support.
- Advanced parking analytics.
- Predictive parking availability.
- Improved reporting and monitoring.

## 🤝 Contributing

Contributions, suggestions, and improvements are welcome.

### Contribution Guidelines

1. Fork the repository.
2. Create a feature branch.

```bash
git checkout -b feature/your-feature-name
```

3. Implement and test your changes.
4. Commit your changes.

```bash
git commit -m "Add: describe your changes"
```

5. Push your branch.

```bash
git push origin feature/your-feature-name
```

6. Open a Pull Request for review.

## 📌 Project Information

| Detail | Information |
|---|---|
| Project Name | Parking Reservation |
| Project Type | Full-Stack Web Application |
| Project Context | Academic Team Project |
| Domain | Parking Reservation and Management |
| Frontend | React.js, Vite |
| Backend | Python, FastAPI |
| Database | PostgreSQL |
| Repository Owner | coretech001 |
| Live Demo | [Explore Project](https://smart-parking-reservation-system-one.vercel.app/) |
| GitHub Repository | [View Repository](https://github.com/coretech001/parking-reservation-platform) |

---

<div align="center">

### Parking Reservation

**Making parking reservations simpler and more convenient.**

Developed as an academic team project.

<br />

[GitHub Profile](https://github.com/coretech001) · [Live Demo](https://smart-parking-reservation-system-one.vercel.app/)

</div>
