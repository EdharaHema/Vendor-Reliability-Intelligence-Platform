# Vendor Reliability Intelligence Platform

## Project Overview

The **Vendor Reliability Intelligence Platform** is a full-stack web application designed to manage vendors, procurement operations, purchase orders, vendor performance, reliability, contracts, compliance, analytics, notifications, and reports in a centralized system.

The platform provides role-based access so that users can access features according to their responsibilities.

---

## Key Features

- Secure user registration and login
- JWT-based authentication
- Role-based access control
- Vendor management
- Procurement request and approval management
- Purchase order management
- Vendor performance tracking
- Vendor reliability analysis
- Contract and compliance management
- Notification center
- Role-specific dashboards
- Analytics and data visualization
- PDF and Excel report generation
- PostgreSQL database integration
- REST APIs using FastAPI

---

## User Roles

The platform supports the following roles:

| Role | Responsibilities |
|------|------------------|
| Administrator | Manage users, roles, and overall system operations |
| Procurement Manager | Manage procurement, vendors, approvals, and purchase orders |
| Supply Chain Manager | Monitor vendor performance, delivery, and reliability |
| Vendor | Manage vendor information and view relevant activities |
| Finance Officer | Monitor financial and procurement-related information |
| Auditor | Review reports, compliance, and operational information |

---

## Technologies Used

### Frontend

- Angular
- TypeScript
- HTML5
- CSS3
- Angular Material
- RxJS
- Reactive Forms
- Chart.js

### Backend

- Python
- FastAPI
- Uvicorn
- SQLAlchemy
- Pydantic
- JWT Authentication
- bcrypt

### Database

- PostgreSQL

### Reporting

- ReportLab
- OpenPyXL
- Matplotlib

### API Documentation

- Swagger / OpenAPI

---

## Project Structure

```text
Vendor-Reliability-Intelligence-Platform/
│
├── backend/
│   ├── app/
│   │   ├── main.py
│   │   ├── models/
│   │   ├── schemas/
│   │   ├── routers/
│   │   ├── services/
│   │   ├── database/
│   │   └── auth/
│   │
│   ├── requirements.txt
│   └── .env
│
├── frontend/
│   ├── src/
│   │   ├── app/
│   │   │   ├── pages/
│   │   │   ├── services/
│   │   │   ├── guards/
│   │   │   └── models/
│   │   ├── assets/
│   │   └── environments/
│   │
│   ├── package.json
│   └── angular.json
│
├── .gitignore
└── README.md
```

---

## Main Modules

### 1. Authentication and Role Management

- User registration
- User login
- Password hashing
- JWT authentication
- Forgot password
- Password reset
- Profile management
- Logout
- Role-based access

### 2. Vendor Management

- Vendor registration
- Vendor information management
- Vendor categorization
- Vendor status
- Vendor profiles
- Vendor performance information

### 3. Procurement Management

- Procurement requests
- Approval workflow
- Department-wise procurement information
- Procurement spending
- Procurement analytics

### 4. Purchase Order Management

- Purchase order creation
- Order tracking
- Order status management
- Vendor-based order tracking
- Delivery tracking

### 5. Vendor Performance and Reliability

- Vendor performance monitoring
- Delivery performance
- Purchase order activity
- Performance summaries
- Vendor reliability analysis

### 6. Contract and Compliance

- Contract management
- Contract details
- Contract status
- Compliance tracking
- Compliance information

### 7. Notifications

- Stored notifications
- Notification center
- Read/unread status
- Backend-persisted notification state

### 8. Dashboards and Analytics

Role-specific dashboards provide information related to:

- Vendors
- Procurement
- Purchase orders
- Delivery
- Contracts
- Compliance
- Performance
- Notifications

### 9. Reports and Export

The system supports:

- Procurement reports
- Vendor performance reports
- Filtered reports
- PDF export
- Excel export

---

## System Architecture

```text
+-----------------------------+
|       Angular Frontend      |
|                             |
| Components | Services       |
| Forms      | Guards         |
| Dashboards | Charts         |
+-------------+---------------+
              |
              | REST API
              v
+-----------------------------+
|       FastAPI Backend       |
|                             |
| Authentication              |
| Authorization               |
| Business Logic              |
| API Routes                  |
| Validation                  |
+-------------+---------------+
              |
              v
+-----------------------------+
|      PostgreSQL Database    |
+-----------------------------+
```

---

## Authentication & RBAC

The application uses JWT-based authentication and role-based access control.

### Authentication

```text
User
 |
 v
Login
 |
 v
Credential Validation
 |
 v
JWT Token
 |
 v
Authenticated User
```

### Role-Based Access

Access is controlled at both frontend and backend levels.

**Frontend:**

- Authentication guards
- Role guards
- Protected routes
- Role-specific navigation

**Backend:**

- JWT validation
- User authentication
- Role verification
- Protected APIs

---

## Database

The application uses **PostgreSQL** for persistent data storage.

The database manages information related to:

- Users
- Vendors
- Procurement
- Purchase orders
- Contracts
- Compliance
- Performance
- Notifications

The backend uses **SQLAlchemy** for database operations.

Database configuration is provided through environment variables.

Example:

```env
DATABASE_URL=your_postgresql_database_url
SECRET_KEY=your_secret_key
```

Sensitive credentials should not be committed to the repository.

---

## API

The backend provides REST APIs using FastAPI.

Major API areas include:

- Authentication
- Users
- Vendors
- Procurement
- Purchase Orders
- Performance
- Reliability
- Contracts
- Compliance
- Notifications
- Analytics
- Reports

FastAPI automatically provides interactive API documentation through Swagger.

---

## Analytics & Reports

The platform provides analytics using backend application data.

Analytics include:

- Vendor analytics
- Procurement analytics
- Delivery information
- Contract information
- Compliance information
- Performance information
- Notification statistics

Reports can be generated using selected filters and exported in:

- PDF format
- Excel format

The Reports and Export module retrieves report data from the backend instead of relying on hardcoded datasets.

---

## How to Run

The project consists of two applications:

```text
Backend  → FastAPI
Frontend → Angular
```

Both applications should be running for the complete system to work.

---

## Backend Setup

Navigate to the backend directory:

```powershell
cd "C:\GitProjects\infosys\infosys project\backend"
```

Create a virtual environment:

```powershell
python -m venv venv
```

Activate the virtual environment:

```powershell
.\venv\Scripts\Activate.ps1
```

Install dependencies:

```powershell
pip install -r requirements.txt
```

Configure the `.env` file:

```env
DATABASE_URL=your_postgresql_database_url
SECRET_KEY=your_secret_key
```

Start the backend:

```powershell
python -m uvicorn app.main:app --reload
```

The backend will be available at:

```text
http://127.0.0.1:8000
```

---

## Frontend Setup

Open another terminal and navigate to the frontend directory:

```powershell
cd "C:\GitProjects\infosys\infosys project\frontend"
```

Install dependencies:

```powershell
npm install
```

Start the Angular application:

```powershell
npm start
```

The frontend will be available at:

```text
http://localhost:4200
```

---

## Application URLs

| Application | URL |
|-------------|-----|
| Frontend | `http://localhost:4200` |
| Backend | `http://127.0.0.1:8000` |
| Swagger API Documentation | `http://127.0.0.1:8000/docs` |

---

## Testing & Verification

The project has been verified through:

- Backend Python compilation
- Frontend TypeScript compilation
- API integration testing
- Dashboard data verification
- Report data verification
- Notification persistence verification
- Backend data integration verification

### Backend Compilation

```powershell
python -m compileall .
```

### Frontend TypeScript Check

```powershell
npx tsc --noEmit
```

The application uses backend data for important dashboards, analytics, reports, and notifications instead of relying on static dummy data.

---

## Security

The application implements:

- JWT authentication
- bcrypt password hashing
- Role-based access control
- Protected frontend routes
- Protected backend APIs
- Input validation
- Environment-based configuration
- Secure password handling

Sensitive information such as database credentials and secret keys should be stored in environment variables.

---

## Conclusion

The **Vendor Reliability Intelligence Platform** provides a centralized solution for vendor management, procurement operations, purchase order tracking, vendor performance, reliability analysis, contract and compliance management, analytics, notifications, and reporting.

The Angular frontend provides an interactive role-based interface, while the FastAPI backend provides secure REST APIs and database integration using PostgreSQL.

The platform brings vendor and procurement-related information into a single system and provides dashboards, analytics, and reports to support effective management and monitoring.