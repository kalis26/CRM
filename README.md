# Next.js CRM (App Router Fundamentals)

A simple CRM web app built with **Next.js (App Router)** for the **Next.js App Router Fundamentals** course.  
It demonstrates routing, layouts, server components, data fetching/mutations, form actions, loading/error states, and basic auth.

## ✨ Features
- Dashboard with KPIs, revenue chart, and latest invoices
- Customers list + searchable table
- Invoices CRUD (create, edit, paginate, delete)
- Loading skeletons and error boundaries
- Server Actions for mutations with revalidation
- Basic authentication middleware & protected routes
- Clean UI with Tailwind CSS

---

## 🧰 Tech Stack
- **Next.js 14** (App Router, Server Components, Route Handlers)
- **TypeScript**
- **Tailwind CSS**
- **Auth.js / NextAuth** (via `auth.ts`, `auth.config.ts`)
- **PostgreSQL** (or any Postgres-compatible provider)
- Deployed on **Vercel** (optional)

---

## 🗺️ Routes Overview
- `/login` — sign-in form
- `/dashboard` — protected layout
  * `/dashboard` (overview) — metrics, chart, latest invoices
  * `/dashboard/customers` — customers table + search
  * `/dashboard/invoices` — list + pagination
  * `/dashboard/invoices/create` — create invoice
  * `/dashboard/invoices/[id]/edit` — edit invoice
- `/query` — example route handler (API)

---

## ⚙️ Getting Started
### 1. Prerequisites
  - Node.js 18+
  - pnpm (recommended) or npm
  - A PostgreSQL database (local or hosted, e.g. Neon/Vercel Postgres)
### 2. Install
  ```
  pnpm install
  # or
  npm install
  ```
### 3. Environment variables
Create a `.env.local` (or `.env`) file in the project root:
```
# PostgreSQL connection string
DATABASE_URL="postgres://user:password@host:port/dbname"

# Auth.js / NextAuth (generate a strong secret)
AUTH_SECRET="your-strong-random-secret"

# Optional, depending on setup
# NEXTAUTH_URL="http://localhost:3000"
# AUTH_URL="http://localhost:3000"
```
`💡 If you followed the course, reuse the same DB you created there.
Ensure required tables exist for customers, invoices, and any metrics used by the dashboard.`
### 4. Dev server
```
pnpm dev
# or
npm run dev
```
Open [http://localhost:3000](http://localhost:3000)
### 5. Build & start (Production)
```
pnpm build && pnpm start
# or
npm run build && npm start
```

---

## 🧪 Scripts
```
{
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "next lint"
  }
}
```

---

## 📸 Screenshots
![Dashboard](app/opengraph-image.png)

---

## 🧭 Learning Notes
This project was built to practice App Router concepts:
  - Server/Client component boundaries
  - Route groups and nested layouts
  - Route handlers for data fetching
  - Server Actions + cache revalidation
  - Progressive UX: loading UI, skeletons, error boundaries

---

## 🔐 Authentication
Auth wiring lives in `auth.ts`, `auth.config.ts`, and `middleware.ts`.
Protects `/dashboard/*` routes and demonstrates a basic session flow for the course context.

---

## 🙌 Acknowledgements
- Next.js team and the App Router Fundamentals course
- Icons/avatars used for demo purposes in `public/customers`

---

## 📝 License
Distributed under the MIT License. See [LICENSE](https://github.com/kalis26/CRM/blob/main/LICENSE) for details.
