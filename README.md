
<div align="center">

# Parking Reservation

### Reservation & Management Platform

A full-stack web application designed to simplify parking reservations and management through online bookings, parking slot availability, digital payment functionality, QR-based vehicle entry and exit, and administrative controls.

<br />

<img src="https://img.shields.io/badge/Frontend-React-61DAFB?logo=react&logoColor=black" />
<img src="https://img.shields.io/badge/Backend-FastAPI-009688?logo=fastapi&logoColor=white" />
<img src="https://img.shields.io/badge/Database-PostgreSQL-4169E1?logo=postgresql&logoColor=white" />
<img src="https://img.shields.io/badge/Language-Python-3776AB?logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/Build-Vite-646CFF?logo=vite&logoColor=white" />

<br /><br />

**Project Status:** Under Development

</div>

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Project Objectives](#-project-objectives)
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

**Parking Reservation** is a web-based parking reservation and management platform designed to improve the parking experience for users and simplify parking operations for administrators.

The platform allows users to discover parking areas, check parking slot availability, make reservations, access booking information, and use QR-based vehicle entry and exit functionality.

Administrators can manage parking areas, parking slots, bookings, registered users, EV charging facilities, and other operational information through a centralized dashboard.

The application combines a React frontend, a FastAPI backend, and a PostgreSQL database to provide an integrated full-stack solution.

## 🎯 Project Objectives

- Simplify the parking reservation process.
- Improve parking space utilization.
- Reduce the time spent searching for available parking.
- Digitize parking reservations and management workflows.
- Provide centralized administrative controls.
- Improve the overall parking experience.
- Organize parking operations through a unified platform.

## ✨ Key Features

### 👤 User Portal

- User registration and secure login.
- Search parking areas and view available parking slots.
- Check slot availability based on date and time.
- Reserve parking slots online.
- View booking history and booking details.
- Access the payment module.
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

- Parking slot availability based on existing bookings.
- Prevention of overlapping reservations.
- Booking status management.
- QR-based vehicle entry verification.
- QR-based vehicle exit verification.
- Booking completion after exit verification.
- Parking slot release after booking completion or cancellation.
- EV charging facility support.
- Indoor parking navigation support.

> **Note:** The availability of payment gateways, external services, IoT sensors, and other integrations depends on their implementation and configuration.

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

### Frontend

The frontend is developed using React.js and Vite, providing separate interfaces for users and administrators.

### Backend

The backend uses Python and FastAPI to handle application logic, authentication, reservation operations, and API requests.

### Database

PostgreSQL stores application data, while SQLAlchemy provides database interaction through an ORM.

## 🏗️ System Architecture

The application follows a client-server architecture.

The React frontend communicates with the FastAPI backend through REST APIs. The backend manages authentication, application logic, request processing, and database operations using SQLAlchemy ORM.

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

The following structure represents the documented project organization.

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

Follow these instructions to set up and run the application locally.

### Prerequisites

Make sure the following tools are installed:

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

Replace the example values with your actual PostgreSQL credentials and a securely generated secret key.

**Important:**

- Never commit your `.env` file to GitHub.
- Never expose database passwords or secret keys.
- Make sure sensitive environment files are included in `.gitignore`.

### 4. Database Setup

1. Start your PostgreSQL server.
2. Create a database named `smartparking`.
3. Configure the database credentials in your `.env` file.
4. Execute the project's database schema or initialization process.
5. Verify that the backend can connect to the database.

### 5. Run the Backend

From the `backend` directory, execute:

```bash
python -m uvicorn app.main:app --reload
```

Backend server:

```text
http://127.0.0.1:8000
```

Interactive API documentation:

```text
http://127.0.0.1:8000/docs
```

### 6. Frontend Setup

Open a second terminal from the repository root.

Navigate to the frontend directory:

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

The frontend development server is usually available at:

```text
http://localhost:5173
```

Open the URL displayed in your terminal if Vite selects a different port.

## 🗄️ Database Information

The application uses PostgreSQL for persistent data storage and SQLAlchemy as its Object Relational Mapper (ORM).

The documented database areas include:

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

Interactive API documentation is available through Swagger UI when the backend server is running.

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

For production deployment, additional security reviews should cover:

- Authorization and access control.
- Input validation.
- Password hashing.
- CORS configuration.
- Secret management.
- Payment security.
- API request validation.

## 🚀 Future Improvements

Potential enhancements for future versions:

- Integration with real-time IoT parking sensors.
- Live parking occupancy monitoring.
- GPS-based navigation to parking locations.
- Additional payment gateway integrations.
- Mobile application support.
- Advanced parking analytics.
- Predictive parking availability.
- Improved operational reporting.
- Cloud deployment and production infrastructure.

## 🌐 Deployment Status

The application is currently not deployed to a public hosting platform.

For now, the application can be configured and executed locally by following the installation instructions above.

Deployment documentation and a public application URL can be added after the hosting environment has been configured.

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
| Project Subtitle | Reservation & Management Platform |
| Project Type | Full-Stack Web Application |
| Project Context | Academic Team Project |
| Domain | Parking Reservation and Management |
| Frontend | React.js, Vite |
| Backend | Python, FastAPI |
| Database | PostgreSQL |
| Repository Owner | coretech001 |
| Repository Name | parking-reservation-platform |
| Deployment Status | Not deployed yet |
| GitHub Repository | [View Repository](https://github.com/coretech001/parking-reservation-platform) |

---

<div align="center">

### Parking Reservation

**Making parking reservations simpler and more convenient.**

Developed as an academic team project.

<br />

[GitHub Profile](https://github.com/coretech001)

</div>
