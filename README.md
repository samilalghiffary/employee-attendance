# Employee Attendance System Architecture

Struktur proyek terpisah antara **Backend** dan **Frontend** dengan teknologi versi terbaru.

---

## 📁 Struktur Direktori

```text
employee-attendance/
├── backend/                  # NestJS + TypeScript + Prisma + PostgreSQL
│   ├── src/
│   │   ├── prisma/           # Prisma contract & schema & client db
│   │   │   ├── contract.prisma
│   │   │   └── db.ts
│   │   ├── prisma.service.ts # Injectable Prisma Service untuk modul NestJS
│   │   ├── app.controller.ts
│   │   ├── app.module.ts     # ConfigModule & PrismaService terdaftar
│   │   ├── app.service.ts
│   │   └── main.ts           # CORS diaktifkan, port 3001, global prefix '/api'
│   ├── .env                  # DATABASE_URL PostgreSQL
│   ├── package.json
│   └── tsconfig.json
│
└── frontend/                 # Next.js 16 (App Router) + React 19 + TypeScript
    ├── src/
    │   ├── app/
    │   │   ├── layout.tsx    # TanStack Query Client Provider terpasang
    │   │   ├── page.tsx      # Dashboard preview terintegrasi
    │   │   └── globals.css   # Tailwind CSS v4 & theme variables
    │   ├── components/
    │   │   ├── providers.tsx # QueryClientProvider + ReactQueryDevtools
    │   │   └── ui/           # Shadcn UI (button, card, badge, input, table, skeleton)
    │   ├── lib/
    │   │   ├── api-client.ts # Axios client instance (baseURL http://localhost:3001/api)
    │   │   └── utils.ts      # cn utility untuk tailwind & clsx
    │   └── stores/
    │       └── use-attendance-store.ts # Zustand global store
    ├── package.json
    └── tsconfig.json
```

---

## 🚀 Panduan Menjalankan

### 1. Menjalankan Backend (`NestJS`)

Buka terminal pertama:

```bash
cd backend

# 1. Sesuaikan string koneksi database PostgreSQL di file .env:
# DATABASE_URL="postgresql://user:password@localhost:5432/employee_attendance?schema=public"

# 2. Jalankan development server:
npm run start:dev
```
*Backend akan berjalan di:* `http://localhost:3001/api`

---

### 2. Menjalankan Frontend (`Next.js`)

Buka terminal kedua:

```bash
cd frontend

# Jalankan Next.js development server:
npm run dev
```
*Frontend akan berjalan di:* `http://localhost:3000`
