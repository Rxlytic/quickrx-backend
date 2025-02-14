# Key Features

### User Roles & Capabilities

- #### Doctor:

  - Register/Login
  - Create/Edit/Delete prescriptions (manual and template-based)
  - Manage prescription templates
  - View and manage appointments
  - View and manage transactions

- #### Assistant:

  - Manage appointments (book/cancel/update)
  - Manage schedules for the doctor
  - Handle transactions

- #### General User (Patient):

  - Register/Login
  - Manage their profile
  - View appointment history
  - Access prescriptions

### Additional Features

- Admin Panel: To manage doctors, assistants, and general users.
- Notifications: Email or SMS reminders for appointments.
- Analytics for Doctors: Track patient trends, prescriptions issued, and revenue.

### Multi-Tenancy Model

- #### Standalone Doctor Mode:

  - A doctor can register independently without being part of a clinic.
  - They get full access to the system as a single entity.
  - They can create their own assistants, manage appointments, and handle transactions.

- #### Clinic Mode (Multiple Doctors):

  - Clinics can have multiple doctors.
  - A clinic admin can register doctors under the clinic.
  - Doctors within a clinic operate independently but within the clinic’s infrastructure.
  - Assistants are assigned to a single doctor and cannot switch between doctors.

# Requirements

- **✅ Doctors can register independently or under a clinic.**
- **✅ Clinics can have multiple doctors.**
- **✅ Doctors can create, edit, and use prescription templates.**
- **✅ Doctors can create assistants who manage appointments, schedules, and transactions.**
- **✅ Patients can book appointments with doctors and access prescriptions.**
- **✅ Assistants can only manage data for their assigned doctor.**
- **✅ Multi-tenancy: A doctor can work alone or inside a clinic without overlap.**

# Technical Architecture

- ### Tech Stack:

  - Backend: Honojs with Bun + DrizzleORM + PostgreSQL
  - Frontend: Nextjs
  - Authentication: JWT for session management and RBAC
  - Deployment: Docker

- ### System Components
  - 📌 User Management Service: Handles authentication and role-based access.
  - 📌 Appointment Service: Manages scheduling and availability.
  - 📌 Prescription Service: Stores and generates prescriptions.
  - 📌 Transaction Service: Tracks doctor revenue and payments.

# Installation

To install dependencies:

```sh
bun install
```

Copy environment variables:

```sh
cp .env.sample .env
```

To run:

```sh
bun run dev
```

open http://localhost:3000
