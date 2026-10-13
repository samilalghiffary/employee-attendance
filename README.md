# Employee Attendance System

A modern full-stack employee attendance tracking application featuring decoupled architecture between **Backend** (NestJS) and **Frontend** (Next.js), managed via **Git Submodules**.

---

## 🌟 System Overview & Features

- **📍 Geolocation Attendance**: High-accuracy browser GPS recording on check-in & check-out with OpenStreetMap pin inspection.
- **⏱️ Smart Policy Tracking**: Dynamic computation of attendance status (`PRESENT`, `LATE`, `ABSENT`), late minutes, and early departure minutes.
- **📊 Real-time Metric Summaries**: Aggregated attendance metrics with date filters (Today, This Week, This Month, Custom) for employees and administrators.
- **🛡️ Role-Based Access Control (RBAC)**: Distinct workflows and views for `ADMIN` and `EMPLOYEE` roles.
- **⚙️ Configurable Company Work Policies**: Dynamic settings for work start/end times and late tolerance thresholds.

---

## 📦 Cloning & Setup Guide

Two setup workflows are available:

---

### Option 1: Clone via Parent Repository (Recommended - Fullstack)

Best for managing both Backend and Frontend within a single parent workspace.

#### A. Clone With Submodules

```bash
git clone --recurse-submodules https://github.com/samilalghiffary/employee-attendance.git
cd employee-attendance
```

#### B. If Cloned Normally (Without Submodule Flag)

If `backend/` or `frontend/` folders are empty:

```bash
git submodule update --init --recursive
```

#### C. Pull Latest Changes across Submodules

```bash
git submodule update --remote --merge
```

---

### Option 2: Clone Standalone (Independent FE / BE)

Best for working exclusively on a single service without Git Submodules.

#### Backend Only

```bash
git clone https://github.com/samilalghiffary/employee-attendance-be.git
cd employee-attendance-be
npm install
# Configure .env (DATABASE_URL, JWT_SECRET)
npm run contract:emit
npm run db:seed
npm run start:dev
```

#### Frontend Only

```bash
git clone https://github.com/samilalghiffary/employee-attendance-fe.git
cd employee-attendance-fe
npm install
# Configure .env.local (NEXT_PUBLIC_API_URL)
npm run dev
```

---

## 📁 Project Structure

```text
employee-attendance/
├── .gitmodules       # Submodule configuration for backend & frontend
├── backend/          # NestJS application (API, Prisma ORM, PostgreSQL)
└── frontend/         # Next.js application (App Router, Tailwind CSS, TanStack Query)
```

---

## 🚀 Getting Started (Quick Run)

### 1. Backend (`NestJS`)

```bash
cd backend

# Install dependencies:
npm install

# Setup environment variables in .env:
# cp .env.example .env

# Emit Prisma contract and seed initial data:
npm run contract:emit
npm run db:seed

# (Optional) Seed realistic 1-month mock attendance data:
npm run db:seed:attendance

# Run development server:
npm run start:dev
```

- **Backend API:** `http://localhost:3001/api`
- **Swagger Documentation:** `http://localhost:3001/api/docs`

---

### 2. Frontend (`Next.js`)

```bash
cd frontend

# Install dependencies:
npm install

# Setup environment variables in .env.local:
# cp .env.example .env.local

# Run development server:
npm run dev
```

- **Frontend Application:** `http://localhost:3000`

---

## 🧪 Testing & Code Quality

Each project contains isolated test and lint suites:

```bash
# Backend Quality Checks
cd backend
npm run test         # Unit tests (Vitest)
npm run test:e2e     # E2E integration tests
npm run lint         # Oxlint fast linter

# Frontend Quality Checks
cd frontend
npm run lint         # ESLint Next.js suite
npm run format:check # Prettier verification
```

---

## 📄 License

UNLICENSED - Internal Project.
