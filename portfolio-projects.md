# Portfolio Project Write-ups

Five projects, extracted from the GitHub repositories.

---

## 1. DataMind AI

**Repo:** https://github.com/Kishore-dev-21/DataMind_AI
**Live demo:** https://data-mind-ai-eken.vercel.app/
**Demo video:** https://youtu.be/Qu4EPjvnV_E

### Tagline
Ask your database questions in plain English — get SQL, charts, and insights back.

### Problem statement
Getting insights out of a database normally requires knowing SQL, understanding the schema and table relationships, and knowing how to chart the result. That locks out everyone who needs the answer but isn't technical, and slows down the people who are.

### Solution
A conversational analytics platform where a user types a question in natural language. Google Gemini reads the live database schema, generates SQL, the backend executes it through a read-only layer, and the app returns the result as a table, an interactive chart, and a plain-English explanation. Alongside the chat there's a full eight-section analytics dashboard over the same data. Built on the Brazilian E-Commerce Public Dataset (Olist) from Kaggle — every number shown is computed from real records, nothing is fabricated.

### Key features
1. **Natural language to SQL** — Gemini interprets the question against the actual schema and writes the query.
2. **Secure read-only execution** — AI-generated SQL is treated as untrusted; DROP, DELETE, UPDATE, INSERT, ALTER and CREATE are blocked at the execution layer.
3. **Schema-aware agent** — the backend feeds table names, columns, data types and relationships to the model before generation.
4. **Dynamic visualization** — results auto-render as bar, line, area, pie or scatter charts via Recharts, with tooltips, hover states and fullscreen expansion.
5. **AI-generated insights** — instead of raw numbers, the model explains trends, comparisons, dominant categories and anomalies.
6. **ER diagram generation** — Mermaid-rendered entity relationship diagrams generated from the live schema on request.
7. **Interactive data explorer** — paginated, sortable, filterable views over orders, customers, products, payments, sellers, reviews and order items.
8. **Eight-module analytics dashboard** — Overview (KPIs), Orders, Revenue, Products, Customers, Explorer, EDA and Data Quality.
9. **Exploratory data analysis** — correlation matrices, distribution histograms and outlier detection.
10. **Data quality monitoring** — null tracking, data freshness and schema validation before AI processing.
11. **Multi-turn conversation** — follow-up questions retain session context, and the generated SQL can be displayed for transparency.

### Technologies used
- **Frontend:** React 19, TypeScript, Vite, Tailwind CSS, TanStack Router, TanStack Query, Zustand, Recharts, Mermaid, Framer Motion, Radix UI, Lucide React, React Markdown
- **Backend:** Python, FastAPI, Uvicorn, Pandas, NumPy, SQLAlchemy, SQLite3
- **AI:** Google Gemini via the Google GenAI SDK
- **Database:** SQLite (Olist Brazilian E-Commerce dataset)
- **Deployment:** Vercel

### Extra details worth using
- **Context:** iTech AI Innovation Hackathon 2026, Sri Sairam Engineering College. Challenge: "Building Intelligent LLM Agents for Database Interaction & Visualization." Team **SwiftTech** (4 members).
- **Agent tool architecture** — five named tools: `get_schema`, `execute_query`, `generate_chart`, `generate_flowchart`, `explain_data`. Good detail for a technical interview.
- **API surface:** `POST /api/ask`, `POST /api/upload`, `GET /health`.
- **Design principle:** deliberately scoped to the connected dataset rather than being a general-purpose chatbot — a defensible engineering decision, not a limitation.
- **Future scope:** PostgreSQL/MySQL connectivity, custom dashboard builder, anomaly detection, RBAC, streaming responses.

---

## 2. EduLink+

**Repo:** https://github.com/Kishore-dev-21/EduLink
**Live demo:** https://leafy-pasca-10c6dd.netlify.app/

### Tagline
A role-based smart campus platform connecting students and staff in one place.

### Problem statement
Campus information is scattered — events on noticeboards, notes in WhatsApp groups, exam schedules in PDFs, scholarships nobody hears about until the deadline passes. Students miss opportunities, and staff have no single channel to reach them or visibility into where students actually need help.

### Solution
A React + TypeScript single-page application with two distinct role-based experiences — Student and Staff — each with its own navigation, dashboard and module set. It centralizes events, study materials, exam schedules, lost-and-found, notifications, scholarships and skill development, and layers an AI assistant and a skill-intelligence engine on top.

### Key features
1. **Role-based access** — separate student and staff interfaces routed off the authenticated user's role.
2. **AI Smart Assistant** — conversational helper that answers campus queries (events, exams, materials, scholarships) without leaving the current page.
3. **Skill Intelligence engine** — students build a skill profile via resume upload, certificate upload or manual selection.
4. **ATS scoring** — resume strength scored against an ATS rubric so students know where they stand before applying.
5. **Opportunity match engine** — ranks internships, jobs, hackathons and scholarships against the student's skill profile.
6. **Application tracker** — end-to-end status tracking (Applied → Shortlisted → Accepted).
7. **Events module** — students browse, filter and register; staff create, edit and manage.
8. **Study materials** — department-wise notes and slides, uploaded and organized by staff.
9. **Exam schedules** — timetables with subject, date and venue; staff publish across departments.
10. **Lost and found** — students report or search; staff moderate and close cases.
11. **Notification broadcast** — targeted or campus-wide alerts with a real-time student-side feed.
12. **Scholarship management** — merit and need-based listings filtered by department, CGPA and skills; staff review the application pipeline.
13. **Staff analytics** — department-level engagement, placement readiness distribution, skill gap heat maps and event participation.

### Technologies used
React 18, TypeScript, Vite 5, Tailwind CSS 3, React Context API (state), Lucide React (icons), date-fns, Supabase (integration layer configured), deployed on Netlify.

### Extra details worth using
- There's an IEEE paper tied to this: *"EduLink+: An AI-Powered Smart Campus Ecosystem"* — worth listing as a linked publication on the portfolio.
- The README documents four Mermaid diagrams (system architecture, user flow, auth/role-routing sequence, skill intelligence flow). Screenshots of these make strong portfolio visuals.
- MIT licensed.
- The data layer is mock data structured for a Supabase swap — frame this as an intentional architecture decision rather than incompleteness.

---

## 3. SGE Innovative Toolcraftt × Aluzin Diecastings

**Repo:** https://github.com/Kishore-dev-21/SGE-Innovative-Toolcraftt-Pvt-Ltd
**Live demo:** https://endtoend-fabricate-main.vercel.app/

### Tagline
A production SSR corporate site for a Chennai precision die-casting manufacturer.

### Problem statement
Small and mid-sized Indian manufacturing firms typically have no credible digital presence. Procurement teams, OEMs and engineering managers evaluating a supplier need to see real capability — machinery, tolerances, certifications, part catalogues — and can't find it, so the firm loses enquiries to competitors who are simply easier to assess online.

### Solution
A server-side-rendered marketing and capability site for two integrated companies (SGE handles PDC mould design and manufacturing; Aluzin handles high-pressure die casting and machining). It presents the full component lifecycle — from 3D CAD modelling through toolroom fabrication, casting, CNC machining and CMM inspection to dispatch — as a navigable eleven-stage journey, with a filterable product catalogue, facility tours, quality documentation and an enquiry form.

### Key features
1. **SSR architecture** — TanStack Start with Nitro for fast first paint and SEO, important for a site whose job is inbound discovery.
2. **Eleven-stage manufacturing workflow** — the component journey from design analysis to logistics dispatch, rendered as an interactive flow.
3. **Filterable product catalogue** — die-cast components across automotive, industrial, electrical, appliance, lighting and valve categories.
4. **Facilities tour pages** — dedicated sections for the 4,800 sq. ft. toolroom and the 4,800 sq. ft. casting floor, with machine-level detail (VMC 640, EDM V5030, 80T/125T/180T HPDC machines).
5. **Quality assurance section** — ISO 9001:2008 pillars, spectro analysis, CMM measurement and inspection architecture.
6. **Custom industrial design system** — OKLCH-based dark palette built on Tailwind CSS v4.
7. **Canvas particle system** — a subtle spark-particle effect (`ParticleCanvas`) suited to the foundry subject matter.
8. **Blueprint overlay** — a precision-engineering grid motif running through the layout.
9. **Scroll-linked motion system** — Framer Motion animations coordinated through a shared `AnimationProvider` context.
10. **Validated enquiry form** — React Hook Form + Zod, with facility location details.

### Technologies used
TanStack Start (SSR), TanStack Router, React 19, TypeScript, Tailwind CSS v4, Framer Motion v11, Radix UI, Lucide React, React Hook Form, Zod, Vite, Nitro. Deployable to Vercel serverless, Cloudflare Pages/Workers or any Node host; Firebase Hosting config also present.

### Extra details worth using
- This is the one **real client / real business** project in the set. Lead with that — it separates it from coursework and hackathon builds.
- Strong talking points: SSR vs. SPA trade-off for a lead-generation site, and designing a visual language (blueprint grids, spark particles, OKLCH industrial palette) that matches a client's industry rather than reaching for a generic template.
- Domain research depth is itself a selling point — the site encodes real manufacturing vocabulary, machine specs and QC processes.

---

## 4. ZENTRIX 2026

**Repo:** https://github.com/Kishore-dev-21/zentrix
**Live site:** https://zentrix-hackathon-2026.surge.sh

### Tagline
The official event platform for a 24-hour national hackathon, built from scratch.

### Problem statement
National-level hackathons run on scattered infrastructure — a Google Form here, a WhatsApp broadcast there, rules in a PDF nobody opens. Participants arrive unclear on the schedule, the rules and how they'll be judged, and the organizing body has no single authoritative source to point at.

### Solution
A single official portal for ZENTRIX 2026, organized by the IEEE Industrial Electronics Society Student Branch Chapter at Sri Sairam Engineering College. It carries the complete event architecture: the eleven-phase operational lifecycle, the hour-by-hour 24-hour schedule, seven technical tracks, fifteen governance rules, the 100-point evaluation rubric, the full organizing structure and the registration funnel — presented through a cyber/gothic themed interface with WebGL visuals.

### Key features
1. **Themed immersive interface** — a distinct cyber/gothic visual identity built as a custom Tailwind design extension rather than a template.
2. **Three.js WebGL layer** — dynamic particle rendering and interactive visual elements.
3. **Eleven-phase event lifecycle** — from check-in and track allocation through to the valedictory ceremony, documented as a navigable flow.
4. **Full 24-hour schedule** — Day 1, overnight phase and Day 2 broken down slot by slot with operational scope for each.
5. **Seven technical track listings** — Industrial Automation & Robotics, Smart Energy, Edge AI & Computer Vision, IoT & Cyber-Physical Systems, Cybersecurity, Healthcare Engineering, Open Innovation.
6. **Fifteen governance rules** — team composition, zero pre-written code, AI tool policy, plagiarism, live-demo requirement, submission deadlines and disqualification protocols.
7. **Transparent evaluation rubric** — the 100-point weighting (Innovation 25, Technical Complexity 25, Prototype Execution 25, Viability 15, Presentation 10) published up front.
8. **Organizational directory** — patrons, faculty advisors, office bearers, domain specialists and volunteers.
9. **Registration integration** — direct funnel into the official registration form.
10. **Custom typography stack** — Clash Display, Space Grotesk and JetBrains Mono.
11. **Static CDN deployment** — Surge.sh with GitHub Pages and a custom domain via CNAME.

### Technologies used
Vanilla ES6+ JavaScript, semantic HTML5, Tailwind CSS 3.x (custom extensions), Three.js (WebGL), Lucide Icons, Vite 5.x, PostCSS, Autoprefixer. Deployed to Surge.sh CDN and GitHub Pages.

### Extra details worth using
- **The role is the headline:** Webmaster and Lead Platform Architect, IEEE IES Student Branch Chapter. This is an official position, not a personal project — say so.
- Built in **vanilla JS rather than a framework**, deliberately, for performance and low overhead. That's a defensible engineering choice worth explaining when asked why there's no React here.
- Event dates: September 30 – October 1, 2026. Real users, real deadline, real stakes.
- Shows range beyond app development: information architecture for a complex real-world process, plus a strong distinct visual identity.

---

## 5. Click2Ration — User Portal

**Repo:** https://github.com/Kishore-dev-21/C2R_User-Portal
**Live demo:**  https://ration-guard-plus-mainmap-1.vercel.app/

### Tagline
A multilingual citizen portal that brings Tamil Nadu's ration system to the doorstep.

### Problem statement
Tamil Nadu's Public Distribution System serves millions of families every month, but the fair-price shop model still means physical queues, paper record-keeping and no visibility into stock or entitlements. Beneficiaries lose a working day to collect rations, have no way to check what they're owed before travelling, and no recourse when a shop is out of stock.

### Solution
A citizen-facing web portal that digitizes the whole ration workflow: log in with a ration card number, verify by OTP, see the household's exact monthly entitlement, order the required commodities, track the delivery agent live on a map, confirm handoff by OTP and download an official PDF receipt. The entire interface runs in English or Tamil, and a built-in chatbot answers questions about allocations and eligibility.

### Key features
1. **Ration card + OTP authentication** — card-number login with 6-digit OTP verification and session-scoped state holding no persistent sensitive data.
2. **Entitlement dashboard** — visual consumption meters, per-household-member quota tracking and current-month balances.
3. **Allocation-aware catalogue** — the product list is filtered by family size and allocation rules, with maximum-limit enforcement on quantity.
4. **Live delivery tracking** — delivery agent movement on an interactive Leaflet map, with agent name, contact and ETA.
5. **Status timeline** — Order Placed → Processing → Dispatched → Out for Delivery → Delivered.
6. **OTP delivery confirmation** — handoff verified by OTP specifically to prevent fraudulent delivery claims.
7. **PDF invoice generation** — one-click official receipt with order ID, itemized quantities and pricing, carrying the Tamil Nadu state header.
8. **RationBot AI assistant** — floating-button chatbot answering allocation, order status, eligibility and scheme queries from any screen.
9. **Full English/Tamil localization** — language toggle persisting across the session, essential for the actual beneficiary population.
10. **Out-of-stock alerts** — notification subscription so citizens know when a commodity returns.
11. **Notification centre** — SMS-simulated in-app messages with unread badges and mark-as-read actions.
12. **Post-delivery rating and feedback** — closing the accountability loop on each delivery.

### Technologies used
React 18, TypeScript, Vite, Tailwind CSS (custom design tokens), shadcn/ui + Radix UI, React Context (LanguageContext), TanStack Query, Supabase (backend/auth), Firebase (real-time database + hosting), Leaflet + React Leaflet, jsPDF, html5-qrcode, React Hook Form + Zod, React Router v6, Recharts, Lucide React.

### Extra details worth using
- This is **one of three portals** in the wider Click2Ration platform (Citizen Portal, Admin Portal with fraud investigation tooling, Delivery Agent field app), backed by a Node.js/Express API and MySQL. Built for **SmartAIthon 2026, Team T697 – SWIFTTECH**. Mention the full system so the scope reads accurately.
- The wider platform includes a nine-stage Fraud Chain Intelligence pipeline using distance, velocity, biometric-failure and geofence heuristics — a strong technical talking point.
- **Accessibility and inclusion** is the real design story here: Tamil-language support, mobile-first, low-literacy-friendly visual meters. Lead the write-up with that.
- Best example in the portfolio of civic-tech / government digital service work.

---

## Portfolio positioning notes

The five projects cover distinctly different ground, which is worth making explicit on the site:

| Project | Category | What it proves |
| --- | --- | --- |
| DataMind AI | AI / LLM engineering | Agent architecture, NL-to-SQL, data security |
| EduLink+ | Full-stack product | Role-based systems, multi-module scope, linked research |
| SGE Toolcraftt | Client work | Real business delivery, SSR, custom design systems |
| ZENTRIX 2026 | Leadership / event tech | Official org role, vanilla JS performance, WebGL |
| Click2Ration | Civic tech | Multilingual accessibility, geolocation, fraud prevention |

Recurring stack across the set — **React + TypeScript + Vite + Tailwind** — makes a clean "core stack" line for the portfolio header, with Python/FastAPI, Gemini, Supabase, Firebase and Three.js as the range around it.

Three of the five have live demos. Put those links above the fold on each project card; they convert far better than a repo link alone.

# 6.DEEPSYNC (DeepsSync-Bluegen)

**Repo:** https://github.com/Dhanush-BT/DeepsSync-Bluegen
**Live demo:** None listed in the repo
**Team:** BLUEGEN_606
**Context:** Smart India Hackathon, PS 26067, INCOIS (Ministry of Earth Sciences)

> **Check this:** the README says **SIH 2025**, but you said SIH 2026. Confirm the year before it goes on a slide or portfolio.

---

## Tagline
A web-based 3D ocean visualization platform that combines model simulations with real instrument data.

## Problem statement
problem statement ID: SIH26067
- Ocean data is split between numerical model outputs (MOM4, HYCOM, NetCDF) and in-situ instruments (Argo floats, gliders, CTD casts, buoys).
- Scientists struggle to view both together, slice them in 3D and over time, and get quick answers.
- Most tools are 2D, desktop-only or need specialist skills.

## Solution
- An interactive web platform that fuses model data and instrument observations in one place.
- It offers volumetric 3D rendering, cross-section slicing, 4D time playback and an AI assistant.
- It is built for scientists, researchers, educators and the public.

---

## Key features

**1. 3D Ocean Scene (`/dashboard`)**
- WebGL2 / Three.js volumetric rendering of temperature, salinity, chlorophyll-a and current vectors (u, v).
- Slicing by latitude, longitude and depth (0 to -6000 m).
- Custom colormaps (Turbo, Viridis, Thermal, Haline, Deep Ocean) and vertical exaggeration.
- Real-time isosurface extraction by threshold.

**2. Instrument GeoMap (`/geomap`)**
- Tracks Argo floats, gliders, CTD casts and moored buoys.
- Drift trajectories, bearing indicators and profile soundings.
- New NetCDF/CSV uploads sync without a page reload.

**3. 2D Diagnostics**
- Depth profile (thermocline, halocline, pycnocline).
- T-S diagram with potential density contours.
- Time series, Hovmöller diagrams, current roses and along-track transects.

**4. AI Assistant (`/assistant`)**
- Natural-language queries grounded in the loaded data.
- Computes Mixed Layer Depth (MLD), identifies water masses and gives hazard advisories.
- Generates charts inside the chat.

**5. Data Manager (`/datamanager`)**
- Ingests NetCDF-3/4, ASCII and CSV.
- Validates against CF-1.8 metadata conventions.
- Auto-links profiles to platform IDs and builds spatial indexes.

---

## Technologies used

| Layer | Stack |
| --- | --- |
| Frontend | React 18, Vite 5, Three.js (`@react-three/fiber`), Tailwind CSS, Leaflet, Chart.js, Zustand |
| Backend | Spring Boot 3.4.0, Java 17, Spring Data JPA, Hibernate, Maven |
| Scientific data | Unidata NetCDF-Java (`cdm-core` 5.6.0), Apache Commons CSV |
| Database | PostgreSQL 16 (PostGIS mentioned in the architecture diagram) |
| Security | JWT with Spring Security |
| Deployment | Docker Compose (config file present) |

## Architecture
- React UI talks over REST to a Spring Boot backend on port 8081.
- The backend uses PostgreSQL for storage and NetCDF-Java for parsing scientific files.

## API endpoints
- `GET /api/ocean-data`: 3D grid points with bounding box, depth and time filters
- `GET /api/ocean-data/axes`: depth slices and time stamps
- `GET /api/floats`: all instruments
- `GET /api/floats/{id}/track`: GPS trajectory
- `GET /api/floats/{id}/profiles`: depth profiles
- `GET /api/stats/summary`: aggregate stats
- `POST /api/admin/ingest`: upload NetCDF/CSV/ASCII
- `POST /api/auth/login` and `/signup`: authentication

## How to run
- **Database:** create a PostgreSQL DB named `deepsync` (port 5433).
- **Backend:** `./mvnw spring-boot:run` (Windows: `.\mvnw.cmd spring-boot:run`)
- **Frontend:** `cd frontend`, then `npm install`, then `npm run dev`, and open `localhost:5173`.
- **Prerequisites:** Java 17+, Node 18+, PostgreSQL 15+.

---

## Extra details worth using
- **Scientific depth:** it handles real oceanographic standards (CF-1.8, NetCDF, MLD, T-S diagrams), which is a strong point for an INCOIS problem statement.
- **Full-stack split:** a Java backend with a React/WebGL frontend, a different mix from your Python and React projects.
- **Repo activity:** 40 commits on `main`.
- **Repo extras:** it includes docs for dataset integration, implementation status and phase tracking, which shows structured project management.
- **AI tooling folders:** `.claude`, `.serena` and `.playwright-mcp` suggest the team used AI coding tools.

## Gaps to know before presenting
- The README names no individual team members or roles, so add yours.
- There is no deployed demo, so a demo video or screenshots would help.
- The AI assistant's model and provider are not stated, so confirm what it uses before you describe it.
- Contributors are not listed on GitHub, so check that your commits are credited.

---

## Slide-ready summary
- **Project:** DEEPSYNC, a 3D ocean visualization and intelligence platform
- **For:** INCOIS, MoES (SIH PS 26067)
- **Core idea:** fuse model data and in-situ observations in one interactive web view
- **Highlights:** 3D volumetric scene, instrument GeoMap, 2D diagnostics, AI assistant, CF-compliant data ingestion
- **Stack:** React, Three.js, Spring Boot, PostgreSQL, NetCDF-Java

To make this portfolio-ready like your other projects, I can add your role, a problem-solution pitch or a Q&A prep list for judges. Tell me your role in the team and which one you want.