# Silkways Group — Full Stack Corporate Website

A full-featured corporate website for **Silkways Group**, a 30-year-old Bangladeshi business conglomerate with 9+ sister concerns spanning aviation, cargo, travel, smart card manufacturing, flexible packaging, manpower recruitment, hospitality, and fine dining. Built end-to-end as a **Full Stack Developer** — from design planning and UI/UX to frontend development, backend API, and deployment — in **1 week**. Production site: **https://silkwaysgroup.com/** — Updated live preview (latest version): **https://silkwaysgroup-v2.vercel.app/**

---

## Summary

Designed and built the Silkways Group corporate website from scratch in 1 week as a Full Stack Developer — owning design planning, frontend, backend API, and deployment. Delivered a multi-page corporate website with a fullscreen animated hero slider across 9 sister concerns, individual dynamic company profile pages, tabbed gallery, categorized FAQ accordion, enterprise pricing section, blog/articles section, booking calendar with contact form, and a backend API with admin panel for content management. Tech stack: React 19, React Router 7 (SSR), TypeScript, Tailwind CSS 4, Framer Motion, Swiper.js, React Hook Form + Zod, Radix UI, Axios — backend: Node.js REST API (Vercel).

---

## Project Overview

| Item | Detail |
|---|---|
| **Live Website** | https://silkwaysgroup.com/ |
| **Updated Live Preview** | https://silkwaysgroup-v2.vercel.app/ ← latest version |
| **Duration** | 1 week |
| **Role** | Full Stack Developer (design → deployment) |
| **Frontend** | React 19, React Router 7 (SSR), TypeScript, Tailwind CSS 4, Framer Motion, Swiper.js, Radix UI, React Hook Form + Zod, Axios, react-fast-marquee, react-day-picker |
| **Backend** | Node.js REST API (Vercel deployment) + Admin Panel |
| **Design** | Designed from scratch — layout planning, section structure, visual hierarchy, component system |

---

## Pages & Routes

| Route | Description |
|---|---|
| `/` | Home — full corporate website with all sections |
| `/sisters-concerns/:slug` | Dynamic individual company profile page per sister concern |

---

## Feature Breakdown

### 1. Hero Section — Fullscreen Animated Slider

The most visually prominent section — a cinematic fullscreen carousel cycling through all 9 sister concerns.

- **Swiper.js** with crossfade effect and 7-second autoplay
- **Ken Burns CSS zoom animation** — subtle scale animation on each active slide background for depth and motion
- **9 slides** — each with a company-specific full-bleed background image, company name, and description
- **Framer Motion stagger animations** — headline and description fade-up with staggered delays on each slide transition
- **Smart linking** — company name links externally if the concern has its own website, otherwise routes to the internal dynamic profile page
- **Custom prev/next navigation** — bottom-right corner controls with hover color transitions
- **Performance optimized** — first slide loads with `fetchPriority="high"` and `decoding="sync"`; all others use `loading="lazy"`

---

### 2. Partner Logos Section

- Horizontally scrolling infinite marquee of global and local partner/client logos
- **react-fast-marquee** for smooth, pauseable auto-scroll

---

### 3. About Section

- Group introduction — founding story (1995), values, and mission overview
- Leadership highlights — Chairman, Managing Director, Advisor
- Key milestones and 30+ years of business achievements

---

### 4. Sister Concerns List

- Grid card layout listing all 9 sister concerns
- Each card: logo, company name, industry category, short description
- Click navigates to the full dynamic company profile page

---

### 5. Mission & Vision Section

- Two-column layout presenting the group's mission and vision statements
- **Circular diagram** component — animated visual representation of group values
- Scroll-triggered Framer Motion entrance animations

---

### 6. Sectors Section

- Showcases the 6 core industries Silkways Group operates in:
  1. Aviation & Airline Representation
  2. Smart Card Manufacturing & Personalization
  3. Visa Facilitation & Embassy Representation
  4. Travel & Logistics Services
  5. Advanced Industrial Polymers & Packaging
  6. Premium Hospitality & Resort Experience
- Two-column masonry-style card grid with alternating heights (420px / 300px)
- Full-bleed background images per sector with glassmorphism text overlay
- Hover reveal — overlay and text slide up on hover (desktop)

---

### 7. Gallery Section

- Tabbed gallery organized by sister concern — **8 company tabs** with animated underline indicator
- **Framer Motion spring animation** on the active tab underline (smooth slide between tabs)
- **15 images per company** arranged in alternating grid layouts (1-large + 2×2 grid, alternating sides per row)
- `AnimatePresence` — animated fade/slide transition between tab content
- All images lazy-loaded

---

### 8. FAQ Section

- **Tabbed accordion** — multiple FAQ categories selectable via Radix UI Tabs
- Category tabs animate in with stagger on scroll
- **Tab switch animation** — content fades + blurs out on exit, fades + unblurs on enter (`AnimatePresence mode="wait"`)
- Each FAQ item expands with Framer Motion accordion height animation
- Radix UI Accordion for accessible keyboard navigation

---

### 9. Pricing Section (Card Programs)

Service pricing for Silkways Card & Printing's enterprise Visa/Mastercard programs — aimed at banks and fintechs.

**Enterprise Programs:**
- Visa / Mastercard Readiness — €12,000–€18,000 (scheme filing, BIN sponsorship, certification)
- Global Processing Bundle — €22,000–€28,000 (multi-region processing, fraud stack, settlement)
- Personalization & Fulfillment — €15,000–€20,000 (card design, materials, fulfillment)
- Program Ops Retainer — €6,000–€9,000/month
- Enterprise Issuing Retainer — €10,000–€14,000/month

**Growth Programs:**
- Debit & Prepaid Kickoff — €6,500
- Credit Program Blueprint — €8,900
- Personalization Lite — €5,500
- Monthly retainer options from €3,500/month

- Pricing cards with featured/highlighted variants
- Radix UI Tabs to toggle between Enterprise and Growth plans
- CTA links to booking section

---

### 10. Latest Articles / Blog Section

- Article card grid showing 3 latest blog posts on the home page
- Each card: category badge, read time, author, title, description, date, "Read more" link
- Category tags (Student Visa, Immigration News, Travel Tips)
- "All Articles" link — routes to full blog listing
- All cards animated in with Framer Motion stagger on scroll

---

### 11. Client Satisfaction Section

- Testimonials and satisfaction highlights from clients and partner organizations

---

### 12. Booking & Contact Section

- **Interactive booking calendar** — `react-day-picker` date picker for scheduling consultations
- **Contact form** — Name, Email, Phone, Message fields
- **React Hook Form + Zod** — full client-side schema validation
- **API call** — `POST /api/send-message` submits to the backend with typed request/response
- Success/error feedback via toast notifications

---

### 13. Sister Concern Dynamic Profile Pages (`/sisters-concerns/:slug`)

Individual full-page profiles for each company — data-driven from a TypeScript-typed data layer (`CompanyDetailsData` interface). Each page has its own SSR meta title and description for SEO.

**Each page includes:**
- Company-specific banner image with name overlay
- **Stats cards** — 3 key metrics (e.g., years of experience, production capacity, license number, ISO certification)
- **About** — full company history and detailed description
- **Services list** — complete service offerings
- **Recruitment categories** (Alomsons) — Professional, Hotel Industry, Driver, Civil Works, Mechanical, Electrical, Automobile — each with sub-items
- **Additional services** list
- **Key features** — 4 highlight cards with title + description
- **Bankers, legal advisor, auditors, trade bodies** (where applicable)
- **Gallery** — company-specific photo grid
- **Contact info** — address, phone, email, social links

#### 9 Sister Concern Profiles:

| Company | Industry | Established |
|---|---|---|
| **Silkways Aviation Systems Ltd.** | Aviation, GSA, Visa Processing | 1995 |
| **Silkways Cargo Services Ltd.** | Freight Forwarding, GSA Malaysia Airlines (2000–2013), Visa Agent Royal Thai Embassy | 1995 |
| **Silkways Tours & Travels Ltd.** | IATA Travel Agency, Official Visa Agent Singapore (2009–2022) | 2008 |
| **Silkways Card & Printing Ltd.** | Smart Card Manufacturing, ISO 9001:2000, EMV Certified, 2.5M cards/month | 2005 |
| **Silkways International Ltd.** | Import/Export, Marine Products, Turnkey Projects | 2003 |
| **Wellpac Polymers Ltd.** | 100% Export Flexible Packaging, 550 ton/month, 60,000 sqft | — |
| **Alomsons Ltd.** | Manpower Recruitment & Overseas Employment, License No. 165 | 1983 |
| **Farisha Hotel & Resort** | 4-Star Hotel & Resort, Chandpur, Bangladesh | — |
| **Silk Spoon** | Authentic Thai Fine Dining Restaurant, Gulshan, Dhaka | 2025 |

---

### 14. Admin Panel

A separate admin panel for managing website content — articles/blog posts, company profiles, gallery images, contact submissions, and site-wide settings. Powers the dynamic content served via the backend API.

---

### 15. Global CTA

- Floating call-to-action button persistent across all pages
- Encourages visitors to get in touch or book a consultation

---

### 16. Footer

- Group logo and description
- Navigation links, sister concern links
- Social media links, address, contact details

---

### 17. Scroll To Top

- Animated button that appears after scrolling down
- Framer Motion entrance/exit animation

---

## Backend API

Node.js REST API deployed on Vercel — powers contact form submission and admin content management.

- **Base URL**: `https://apisilkwaysgroup.vercel.app/api`
- `POST /api/send-message` — contact/booking form submissions (name, email, phone, message)
- Additional endpoints for blog/article management via admin panel

---

## Architecture & Technical Highlights

- **React Router 7 with SSR** — server-side rendering for fast initial load and per-page SEO meta tags; each sister concern dynamic page has its own `meta()` export
- **Designed from scratch** — full ownership of UI/UX: layout planning, section structure, typography scale, color system, animation system, component hierarchy — no template used
- **Lazy loading & Suspense** — all non-critical home sections wrapped in `React.Suspense` with skeleton fallbacks; hero loads immediately, rest defers for performance
- **Image performance** — first hero slide: `fetchPriority="high"`, `decoding="sync"`; all others: `loading="lazy"`, `decoding="async"`
- **Typed data layer** — all 9 company profiles defined as `CompanyDetailsData` TypeScript interface; single source of truth, fully type-safe
- **Animation system** — Framer Motion throughout: hero stagger, scroll-reveal (`useInView`), `AnimatePresence` for tab transitions, spring underline, accordion height
- **Swiper.js** — crossfade effect with Ken Burns zoom for the hero; Autoplay + EffectFade modules
- **react-fast-marquee** — infinite scrolling partner logos
- **react-day-picker** — calendar date picker in booking section
- **Form system** — React Hook Form + Zod schema validation; Axios for typed API calls
- **Radix UI** — accessible Accordion (FAQ), Tabs (FAQ categories, Pricing plans), Sheet (mobile nav drawer), Dialog
- **Tailwind CSS 4** — utility-first with `tw-animate-css` and custom CSS animations (`hero-zoom-soft` keyframe)
- **Mobile nav** — separate `MobileNavbar` using Radix Sheet/drawer pattern for responsive navigation
