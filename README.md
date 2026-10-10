# Employee Attendance System

A modern full-stack employee attendance tracking application featuring decoupled architecture between **Backend** (NestJS) and **Frontend** (Next.js), managed via **Git Submodules**.

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
# Configure .env (DATABASE_URL)
npm run start:dev
```

#### Frontend Only
```bash
git clone https://github.com/samilalghiffary/employee-attendance-fe.git
cd employee-attendance-fe
npm install
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

## 🚀 Getting Started

### 1. Backend (`NestJS`)

```bash
cd backend

# Install dependencies:
npm install

# Setup environment variables in .env:
# DATABASE_URL="postgresql://user:password@localhost:5432/employee_attendance?schema=public"

# Run development server:
npm run start:dev
```

_Backend runs at:_ `http://localhost:3001/api`

---

### 2. Frontend (`Next.js`)

```bash
cd frontend

# Install dependencies:
npm install

# Run development server:
npm run dev
```

_Frontend runs at:_ `http://localhost:3000`
