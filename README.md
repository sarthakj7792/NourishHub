# NourishLink — Local Food Bank & Surplus Rescue Network

A full-stack, mission-critical community food distribution platform that connects **Food Donors** (supermarkets, bakeries, community gardens), **Food Banks & Pantries**, and **Recipients in Need**.

Built specifically for the **House of Edtech Fullstack Developer Assignment** by **Sarthak Sethi**.

---

## 🌟 Key Highlights & Engineering Features

1. **Full-Stack Next.js 16 (App Router & Turbopack)**:
   - Built with Next.js 16, React 19, TypeScript, and modern Server Components/Client Components separation.
   - Comprehensive RESTful API routes (`/api/donations`, `/api/requests`, `/api/food-banks`, `/api/stats`, `/api/ai/match`, `/api/auth/*`).
2. **WCAG AAA Accessibility & High-Contrast Mode**:
   - Custom **High Contrast Engine** (`data-contrast="high"`) specifically engineered for visually impaired community members and low-vision seniors.
   - Dynamic **Font Scaling** (`A`, `A+`, `A++`), accessible keyboard focus rings (`:focus-visible`), and screen-reader skip links (`#main-content`).
3. **Database Architecture & Robust CRUD**:
   - **PostgreSQL / SQLite ready** with **Prisma ORM**.
   - Complete CRUD operations for **Food Donations** (Donor Portal), **Food Requests** (Recipient Confidential Portal), and **Inventory Logistics** (Pantry Operations).
   - Relations for Donors, Recipients, Food Banks, Donations, and Distribution Logs.
4. **AI-Powered Perishability Triage & Algorithmic Matching**:
   - **AI Shelf-Life Triage**: Calculates dynamic perishability urgency (1-100 score), danger multipliers based on storage condition (ambient vs refrigerated vs frozen), and automated dietary tag categorization.
   - **Algorithmic Needs Matcher**: Correlates unreserved incoming donations to waiting families based on dietary tags (Halal, Gluten-Free, Diabetic-Friendly, Vegan), household sizing, and urgency tiers.
5. **Security & Privacy by Design**:
   - JWT sessions with HTTP-only secure cookies and Role-Based Access Control (`DONOR`, `RECIPIENT`, `ADMIN`).
   - Password hashing with `bcryptjs`, and strict input sanitization via **Zod schemas**.
6. **Automated Testing & Production Readiness**:
   - Comprehensive test suite powered by **Vitest**.
   - Production bundle compiled with zero type or build errors.

---

## 🚀 Quick Start (Running Locally)

### 1. Prerequisites
- Node.js 18+ (Tested on v25.6.1)
- npm 10+

### 2. Installation
```bash
git clone <your-repo-url>
cd <project-folder>
npm install
```

### 3. Database Setup & Seeding
The project is configured out-of-the-box with SQLite for instant zero-friction local execution, and can be connected to PostgreSQL (Neon, Supabase, or AWS RDS) by updating `DATABASE_URL` in `.env`.

```bash
# Push database schema
npx prisma db push

# Generate Prisma Client
npx prisma generate

# Seed sample data (Food banks, donors, perishables, and recipient requests)
npx tsx prisma/seed.ts
```

### 4. Run Development Server
```bash
npm run dev
```
Open **[http://localhost:3000](http://localhost:3000)** in your browser.

---

## 🔑 Demo Credentials (1-Click Login Available)

For quick reviewer evaluation, the `/login` page includes **1-Click Demo Fill Buttons**:

| Role | Email | Password | Primary Portal |
| :--- | :--- | :--- | :--- |
| **Donor** | `donor@freshharvest.com` | `password123` | `/donor` (List, manage, and edit surplus food) |
| **Recipient** | `maria.recipient@gmail.com` | `password123` | `/recipient` (Confidential grocery & dietary requests) |
| **Pantry Admin** | `admin@nourishlink.org` | `password123` | `/admin` (Pantry dispatch & AI matching engine) |

---

## 🧪 Testing

Run the automated test suites:
```bash
npm test
```

Build verification:
```bash
npm run build
```

---

## 👤 Developer Profile & Attribution

- **Name**: Sarthak Sethi
- **GitHub**: [github.com/sarthakj7792](https://www.github.com/sarthakj7792)
- **LinkedIn**: [linkedin.com/in/sarthaksethi5](https://www.linkedin.com/in/sarthaksethi5)
- **Assignment**: House of Edtech — Fullstack Developer Fulltime Assignment
