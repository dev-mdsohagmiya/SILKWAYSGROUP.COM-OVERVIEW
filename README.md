# Silkways Group — Full Stack Corporate Landing Page

A premium corporate group website for **Silkways Group**, a 30-year-old Bangladeshi business conglomerate with 9+ sister concerns spanning aviation, cargo, travel, manufacturing, hospitality, and international trade. Built end-to-end as a **Full Stack Developer** — from design planning to deployment — in **1 week**. Live at **https://silkwaysgroup.com/** and **https://silkwaysgroup-v2.vercel.app/**

---

## Summary

Designed and built the Silkways Group corporate website from scratch in 1 week as a Full Stack Developer — handling UI/UX design planning, frontend development, and backend API integration. Delivered a high-performance, fully responsive corporate landing page showcasing 9 sister concerns, with an animated fullscreen hero slider, individual dynamic company detail pages, a booking/contact system, and a REST API backend. Tech stack: React 19, React Router 7 (SSR), TypeScript, Tailwind CSS 4, Framer Motion, Swiper.js, React Hook Form + Zod, Radix UI, Axios — backend: Node.js (REST API, Vercel deployment).

---

## Project Overview

| Item | Detail |
|---|---|
| **Live Website** | https://silkwaysgroup.com/ |
| **Preview** | https://silkwaysgroup-v2.vercel.app/ |
| **Duration** | 1 week |
| **Role** | Full Stack Developer (design planning → deployment) |
| **Frontend** | React 19, React Router 7 (SSR), TypeScript, Tailwind CSS 4, Framer Motion, Swiper.js, Radix UI, React Hook Form + Zod, Axios |
| **Backend** | Node.js REST API (deployed on Vercel) |
| **Design** | Designed from scratch — layout, sections, visual hierarchy, component system |

---

## Feature Breakdown

### 1. Hero Section — Fullscreen Animated Slider

The most visually prominent part of the site — a fullscreen slideshow showcasing all 9 sister concerns.

- **Swiper.js** with crossfade effect and 7-second autoplay — smooth cinematic transitions between slides
- **Ken Burns zoom animation** — subtle CSS zoom on each active slide background image for depth
- **9 slides** — one per sister concern, each with its own background image, company name, and description
- **Framer Motion** stagger animations — company name and description animate in with staggered fade-up on each slide change
- **Smart linking** — company name links to external website if the concern has one, otherwise routes to the internal detail page (`/sisters-concerns/:slug`)
- **Custom prev/next controls** — bottom-right corner navigation buttons with hover color transitions
- **Performance optimized** — first slide loads eagerly (`fetchPriority="high"`), all others lazy-loaded

---

### 2. Partner Logos Section

- Horizontally scrolling marquee of partner/client logos
- **react-fast-marquee** for smooth infinite scroll animation
- Showcases global and local partner brands

---

### 3. About Section

- Group introduction — founding story, values, mission overview
- Key achievements and milestones since 1995
- Leadership mention — Chairman, Managing Director, Advisor

---

### 4. Sister Concerns List

- Grid/card layout listing all 9 sister concerns
- Each card: company logo, name, industry category, short description
- Click → navigates to the full detail page (`/sisters-concerns/:slug`)

---

### 5. Mission & Vision Section

- Two-column layout with mission statement and vision statement
- Circular diagram component — visual representation of group values/goals
- Animated on scroll via Framer Motion

---

### 6. Sectors Section

- Showcases all industries the Silkways Group operates in:
  - Aviation
  - Freight Forwarding & Cargo
  - Travel & Tourism
  - Smart Card Manufacturing
  - International Trade & Export
  - Flexible Packaging Manufacturing
  - Manpower Recruitment
  - Hotel & Hospitality
  - Food & Fine Dining
- Visual icon + label cards per sector

---

### 7. Client Satisfaction Section

- Testimonials or satisfaction stats
- Progress/percentage stats displayed visually

---

### 8. Booking / Contact Section

- **Interactive booking calendar** — `react-day-picker` for date selection
- **Contact form** — Name, email, phone, message fields
- **React Hook Form + Zod** — full client-side validation
- **API integration** — form submits to `POST /api/send-message` on the backend
- Toast notification on success/error

---

### 9. Sister Concern Detail Pages (`/sisters-concerns/:slug`)

Dynamic pages — one per sister concern — with full company profiles. Data-driven from a typed TypeScript data layer.

Each page includes:
- **Hero banner** — company-specific banner image with company name overlay
- **Stats cards** — 3 key stats per company (e.g., years of experience, production capacity, license number)
- **About** — full company history and description
- **Services list** — complete list of services offered
- **Recruitment Categories** (where applicable) — e.g., Alomsons shows Professional, Hotel Industry, Driver, Civil Works, Mechanical, Electrical, Automobile categories with items
- **Additional Services** — extended service details
- **Key Features** — 4 highlight cards per company
- **Bankers / Legal / Auditors / Trade Bodies** (where applicable)
- **Gallery** — photo grid of company images
- **Contact info** — address, phone, email, social links (where available)

#### Sister Concerns Covered (9 companies):

| Company | Industry | Est. |
|---|---|---|
| **Silkways Aviation Systems Ltd.** | Aviation, GSA, Visa Processing | 1995 |
| **Silkways Cargo Services Ltd.** | Freight Forwarding, GSA (Malaysia Airlines 2000–2013), Visa Agent (Royal Thai Embassy) | 1995 |
| **Silkways Tours & Travels Ltd.** | IATA Travel Agency, Visa Agent (Singapore 2009–2022) | 2008 |
| **Silkways Card & Printing Ltd.** | Smart Card Manufacturing (ISO 9001:2000, 2.5M cards/month) | 2005 |
| **Silkways International Ltd.** | Import/Export, Marine Products, Turnkey Projects | 2003 |
| **Wellpac Polymers Ltd.** | 100% Export Flexible Packaging (550 ton/month, 60,000 sqft) | — |
| **Alomsons Ltd.** | Manpower Recruitment & Overseas Employment (License No. 165) | 1983 |
| **Farisha Hotel & Resort** | 4-Star Hotel & Resort, Chandpur, Bangladesh | — |
| **Silk Spoon** | Authentic Thai Fine Dining Restaurant, Gulshan, Dhaka | 2025 |

---

### 10. Global CTA

- Floating or sticky call-to-action button visible across all pages
- Encourages visitors to get in touch or book a consultation

---

### 11. Footer

- Company logo, group description
- Navigation links
- Sister concern links
- Social media links
- Address and contact details

---

### 12. Scroll To Top

- Smooth scroll-to-top button that appears after scrolling down
- Framer Motion animated entrance/exit

---

## Backend API

Simple REST API deployed on Vercel powering the contact/booking form.

- **Base URL**: `https://apisilkwaysgroup.vercel.app/api`
- `POST /send-message` — receives contact form submissions (name, email, phone, message) and handles delivery

---

## Architecture & Technical Highlights

- **React Router 7 (SSR)** — server-side rendering for fast initial page load and SEO; each sister concern detail page has its own dynamic meta title and description
- **Lazy loading** — all non-critical home sections wrapped in `React.Suspense` with skeleton fallbacks; hero loads immediately, rest defers
- **Performance** — hero images use `fetchPriority="high"` for first slide, `loading="lazy"` for all others; zero layout shift on load
- **Design from scratch** — full UI/UX design ownership: layout planning, section structure, typography, color system, component hierarchy — no template used
- **Typed data layer** — all 9 sister concern profiles defined as TypeScript interfaces (`CompanyDetailsData`) with full type safety; single source of truth for all detail pages
- **Animation system** — Framer Motion used for hero text stagger, scroll-reveal effects on sections, and UI micro-interactions; Swiper.js for the hero carousel
- **Form system** — React Hook Form + Zod schema validation on the contact form; Axios for API calls with typed request/response interfaces
- **Tailwind CSS 4** — utility-first styling with `tw-animate-css` for additional animation utilities
- **Radix UI** — accessible primitives for accordion (FAQ), tabs, dialog, sheet (mobile nav)
- **Mobile nav** — separate `MobileNavbar` component with sheet/drawer pattern for responsive navigation
- **Scroll reveal** — custom `scroll-reveal` UI component for section entrance animations
- **Shine border** — decorative animated border component on feature cards
- **Magic loader** — custom loading animation component
