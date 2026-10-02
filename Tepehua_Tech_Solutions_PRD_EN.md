# Product Requirements Document (PRD) / Master Development Instructions
## Project: Official Corporate Website and Product Showcase for Tepehua Tech Solutions
*   **Version:** 2.0 (Definitive for Development Agent)
*   **Author/Owner:** Ramiro Tepehua Cortes
*   **Mandatory Tech Stack:** Astro (v4+), Tailwind CSS, TypeScript, Semantic HTML5.
*   **Deployment Target:** Self-hosted / Optimized Docker container.

---

## 1. UI/UX VISION AND GUIDELINES (IMPACTFUL, PROFESSIONAL, AND MODERN)
To achieve a highly striking, eye-catching, and professional user interface (UI) that builds instant trust with institutional and local clients, the following visual design principles will be applied:

*   **High-Performance "Dark Mode First" Aesthetic:** The primary background of the web application will be a deep, sophisticated tone simulating high-end server and development environments.
*   **Luminous Contrast (Glow Effects):** Strategic use of bright electric cyan accents over dark backgrounds to guide user attention toward primary Calls to Action (CTAs) and key interactive elements.
*   **Micro-interactions and Fluidity:** Smooth hover transitions (card elevation effects, subtle gradient-illuminated borders) and geometric high-legibility typography.

### Official Brand Color Palette (Mandatory in Tailwind Config)
*   `bg-server` (`#0B192C`): Dominant background for the page and main sections.
*   `card-surface` (`#1E3E62`): Surfaces for cards, product containers, and navigation bars.
*   `accent-cyan` (`#00D1FF`): Interactive color for primary buttons, focal points, active borders, and glow effects.
*   `text-light` (`#F8FAFC`): Structured white for titles and high-priority text.
*   `text-muted` (`#94A3B8`): Technical gray for subtitles and secondary descriptions.

### Corporate Typography
*   **Typeface Family:** *Inter* (Imported via Google Fonts).
*   **Hierarchy:** Main headings in `font-bold` with tight letter spacing (`tracking-tight`); body texts in `font-normal` with optimized line height (`leading-relaxed`).

---

## 2. SITE ARCHITECTURE AND ROUTES (SITEMAP)
The website will be a statically optimized multi-page SPA built via Astro, structured as follows:
1.  `/` (Index / Home): Presentation page, technical authority, and direct access to solutions.
2.  `/soluciones/mensajero-pro`: Commercial and informational landing page for the flagship product.
3.  `/servicios`: Detailed custom software development and infrastructure technical support.
4.  `/blog`: Technical articles, automation, and optimization guides.
5.  `/faq`: Interactive Frequently Asked Questions in accordion format.
6.  `/contacto`: Contact form and direct communication channels (WhatsApp Business).

---

## 3. TECHNICAL SPECIFICATIONS AND CONTENT BY SECTION (EXHAUSTIVE)

### 3.1. Global Component: Navigation Bar (Navbar)
*   **Design:** Fixed at the top (`sticky top-0`), with a semi-transparent glass effect background (`backdrop-blur-md bg-[#0B192C]/80`) and a subtle bottom border (`border-b border-[#1E3E62]`).
*   **Left Elements:** Official isotype (Hexagonal shield with the "T" and network nodes in cyan) followed by the corporate text **TEPEHUA TECH SOLUTIONS**.
*   **Right Elements (Link Menu):** Home, Solutions (Mensajero Pro), Services, Blog, FAQ, and a highlighted CTA button with `#00D1FF` background, `#0B192C` text, and rounded corners (`rounded-lg font-semibold`) reading "Contact / WhatsApp".

### 3.2. Home Page (`/`)
*   **Hero Section (Maximum Visual Impact):**
    *   *Background:* Subtle radial gradient from `#1E3E62` to `#0B192C` with low-opacity code line or network node patterns.
    *   *Top Badge:* "Systems Engineering and Software with over 18 years of experience in Tlaxcala."
    *   *Main Headline (H1):* "Robust systems, custom software development, and intelligent automation for your business."
    *   *Subtitle:* "We transform complex operational challenges into secure, scalable software solutions 100% under your control."
    *   *Action Buttons (CTAs):* 
        *   Primary: "Discover Mensajero Pro" (Links to `/soluciones/mensajero-pro`).
        *   Secondary: "Explore Services" (Links to `/servicios`).
    *   *Visual Element:* Interactive mockup or floating graphical representation of a clean terminal or software interface executing data flows.
*   **Authority & Technical Pillars Section:**
    *   Three floating cards with `card-surface` background (`#1E3E62`) and interactive hover borders:
        1.  *Mission-Critical Architecture:* Robust Full-Stack development (Node.js, Astro, Angular, NestJS, Go, .NET).
        2.  *Privacy and Local Control:* Infrastructure based on secure local databases (SQLite, PostgreSQL) with no mandatory dependency on vulnerable third-party clouds.
        3.  *Intelligent Automation:* Direct connection of workflows and messaging tools (WhatsApp Business API / Desktop).
*   **Featured Section: Mensajero Pro:**
    *   A full-width banner featuring advanced tech-card design presenting the verification center software, highlighting automatic calculation of verification dates and local SQLite database.

### 3.3. Solution Page: Mensajero Pro (`/soluciones/mensajero-pro`)
*   **Product Header:** Main title: *"Mensajero Pro: Intelligent Management and Alerts for Vehicle Verification Centers"*.
*   **Problem vs. Solution:**
    *   *The Problem:* Loss of recurring clients due to missed vehicle verification deadlines and the saturation of manual tasks.
    *   *The Solution:* Optimized desktop software that automates the dispatch of direct WhatsApp reminders strictly following the official Tlaxcala calendar.
*   **Technical Features Grid (Bento Grid):**
    *   *Precise Calculation:* Algorithm based on sticker color and license plate termination.
    *   *Absolute Privacy (100% Local):* Secure local storage in SQLite on the business's own hardware.
    *   *Zero Friction:* Automated dispatch directly to the end customer's WhatsApp.
*   **Commercial Call to Action:** Massive button to schedule a demonstration or request a license.

### 3.4. Services Page (`/servicios`)
*   **Detailed High-Impact Card Listing:**
    1.  *Custom Full-Stack Software Development:* Creation of web apps, desktop apps (Electron), and APIs designed to resolve specific operational bottlenecks.
    2.  *Systems Maintenance and Infrastructure (RenovaPC):* Diagnostics, hardware optimization, equipment refurbishment, and specialized technical support with over 18 years of background.
    3.  *Process Automation and Digitalization:* Implementation of automated workflows to streamline internal administration for local businesses and offices.

### 3.5. Technical Blog Section (`/blog`)
*   Clean grid design to display articles and technical notes written in Markdown (Native Astro support).
*   Card-style article components with date, estimated read time, title, and category tags (e.g., *Automation*, *Debian Linux*, *Databases*).

### 3.6. Frequently Asked Questions Section (`/faq`)
*   Implementation of interactive accordions (using lightweight native JavaScript or Astro components) to directly answer:
    *   *How does Mensajero Pro guarantee my customers' data privacy?* (Explaining SQLite usage and local storage).
    *   *What types of businesses can use Mensajero Pro?* (Verification centers and auto repair shops).
    *   *How are custom development services contracted?*
    *   *What technical support is included after implementing a system?*

### 3.7. Contact Page (`/contacto`)
*   **Structure:** Two symmetrical columns on desktop.
    *   *Left Column:* Direct contact info (Location: Tlaxcala Capital, corporate email, direct links to official channels).
    *   *Right Column:* Interactive contact form (Name, Phone/WhatsApp, Required Service Type, Message) with frontend validation and an electric cyan styled submit button (`#00D1FF`).

---

## 4. TECHNICAL AND PERFORMANCE REQUIREMENTS FOR DEVELOPMENT AGENT (PI)

1.  **Astro Directory Structure:**
    *   `/src/layouts/Layout.astro` (Contains global head, *Inter* font import, SEO metadata, and fixed `Navbar` and `Footer` components).
    *   `/src/components/` (Reusable components: `Hero.astro`, `FeatureCard.astro`, `FaqAccordion.astro`, `PricingCard.astro`).
    *   `/src/pages/` (Main pages in lowercase with hyphens: `index.astro`, `servicios.astro`, `faq.astro`, `contacto.astro`, and `/soluciones/mensajero-pro.astro` subdirectory).
    *   `/src/styles/global.css` (Tailwind CSS configuration with custom corporate color classes).
2.  **Optimization and Accessibility:**
    *   Total static generation (SSG) for instant load performance (Lighthouse > 95 across all metrics).
    *   Mandatory `alt` attributes on all images and semantic tags (`<header>`, `<main>`, `<section>`, `<footer>`).
    *   Fully responsive design optimized from 320px mobile screens up to 4K monitors.
