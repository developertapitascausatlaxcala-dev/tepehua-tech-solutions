# Proposal: Tepehua Tech Solutions Corporate Website (v2.0)

## Intent
Build the official corporate website and product showcase for Tepehua Tech Solutions as a statically generated Astro (v4+) site using Tailwind CSS, TypeScript, semantic HTML5, and the Inter font. The site must establish professional trust with institutional clients through a dark-mode-first aesthetic with cyan accent glow effects, feature the flagship product Mensajero Pro, and provide clear service descriptions, a technical blog, interactive FAQ, and a contact form.

## Scope
**In scope (first product slice):**
- Project initialization: Astro v4 + TypeScript + Tailwind CSS with custom brand palette (`bg-server` `#0B192C`, `card-surface` `#1E3E62`, `accent-cyan` `#00D1FF`, `text-light` `#F8FAFC`, `text-muted` `#94A3B8`).
- Global layout (`Layout.astro`) with Inter font import, SEO meta, fixed Navbar (glass effect, cyan CTA), and Footer.
- 6 routes/pages: `/` (Home/Hero + Authority Cards + Featured Banner), `/soluciones/mensajero-pro`, `/servicios`, `/blog` (Markdown-based Astro native), `/faq` (accordion), `/contacto` (two-column form + channels).
- Component library: `Hero.astro`, `FeatureCard.astro`, `FaqAccordion.astro`, `PricingCard.astro`.
- Responsive design (320px to 4K), semantic HTML (`<header>`, `<main>`, `<section>`, `<footer>`), mandatory `alt` attributes, Lighthouse > 95 target, total SSG.
- Deployment target definition (Docker/optimized container) without full CI pipeline setup.

**Out of scope / later refinement:**
- Actual blog content (placeholder Markdown files only).
- Logo/isotype asset generation (placeholder icon/symbol used; final asset to be inserted later).
- Full email backend integration for `/contacto` (frontend validation + static submission placeholder; backend handler can be added later).
- Production CI/CD pipeline beyond basic Dockerfile definition.
- Performance optimization beyond standard Astro SSG and Tailwind purging.

**Non-goals (must stay unchanged):**
- PRD brand palette, typography rules, and color class names must be preserved exactly.
- Astro + Tailwind + TypeScript stack is mandatory and must not be substituted.
- Site must remain statically generated; server-side rendering or dynamic API endpoints are out of scope.

## Affected Areas
- New repository initialization (currently only `.gitignore` and PRD exist).
- `src/` directory structure: `layouts/`, `components/`, `pages/`, `styles/`.
- Navigation, footer, and SEO metadata (global layout) impact all pages.
- FAQ interactive component requires lightweight native JS or Astro component logic.
- Blog requires Markdown content directory and Astro native content collections setup.
- Deployment requires Docker/container optimization definition.

## Risks
- **Asset gap:** No logo/isotype file is present; the site needs a hexagonal shield isotype. Without it, brand identity is incomplete.
- **Interactive component quality:** FAQ accordion and terminal mockup visual elements need careful implementation to maintain performance.
- **Performance target risk:** Lighthouse > 95 requires strict image optimization, minimal JS, and clean CSS; interactive elements could degrade scores.
- **Deployment ambiguity:** Self-hosted Docker target is defined but build/serve commands and environment variables are not specified in PRD.
- **Content gap:** Blog and FAQ content are partially defined; final text may require updates after review by the business owner.

## Rollback
Since this is a greenfield build (no existing site), rollback is straightforward: revert the `src/` and `public/` directories and delete the Astro build artifacts. If deployment containers are created but not promoted, the existing hosting environment remains unaffected.

## Success Criteria
- All 6 sitemap routes render correctly with correct layout, navigation, and footer.
- Brand palette and typography applied exactly per PRD (custom Tailwind config in `global.css`).
- Lighthouse score > 95 on `/` and `/soluciones/mensajero-pro`.
- All images include `alt` attributes; all pages use semantic HTML.
- FAQ accordion is interactive; contact form validates inputs on the frontend; WhatsApp links are present.
- Docker deployment config exists and the site can be served statically from an optimized container.

## Technical Approach
- Initialize Astro v4 project with TypeScript (`astro init` with TypeScript strict mode).
- Configure Tailwind with custom colors in `tailwind.config.mjs` (or `global.css` with `@theme` for Tailwind v4) mapping the brand palette exactly.
- Build reusable components first (`Hero`, `FeatureCard`, `FaqAccordion`, `PricingCard`), then assemble pages.
- Implement `Layout.astro` with global head, Navbar, Footer, and SEO metadata (title, description, Open Graph basics).
- Create Markdown article stubs in `src/content/blog/` for Astro content collections.
- Implement FAQ with lightweight JS (`details/summary` or minimal Alpine-style click handler) to avoid heavy dependencies.
- Add `Dockerfile` for optimized static serving (e.g., `nginx:alpine` or Astro preview adapter with static build).

---

## Proposal Question Round (Pending User Review)

Before finalizing the implementation plan, please confirm the following open questions so the proposal remains accurate and avoids overbuild:

1. **Business problem / urgency:** The PRD describes lost recurring clients from missed verification deadlines and manual task saturation as the core problem driving Mensajero Pro. Is the immediate goal for this website to generate demo/license requests for that product, or is the broader goal to establish institutional credibility for custom development services as well? This affects which CTA should be visually dominant (primary vs. secondary).

2. **Business rules / content ownership:** For `/contacto`, the PRD defines a form (Name, Phone/WhatsApp, Service Type, Message) but does not specify which email or webhook receives submissions. Should the proposal assume a static form (frontend validation only, no backend handler) for the first slice, or is there an existing endpoint/service we must integrate?

3. **Scope boundary / blog content:** The blog is defined as Markdown-based Astro native with card-style articles. Should the first slice include only placeholder Markdown files (empty article stubs), or is there existing technical content (e.g., automation guides, Debian Linux articles) that must be migrated and formatted before launch?

4. **Edge cases / asset availability:** The PRD requires an official isotype (hexagonal shield with cyan "T" + network nodes). There is no asset file in the repository. Should the proposal assume a placeholder SVG/icon will be inserted, or is a design file available that I should look for in a specific directory?

5. **Deployment and performance tradeoffs:** The PRD targets Lighthouse > 95 and total SSG, with deployment via an optimized Docker container. Should the proposal include a basic `Dockerfile` (e.g., `nginx` serving the static dist) as part of the first slice, or is deployment configuration explicitly deferred until after site delivery?

## Assumptions (Preliminary)
- The site will be built from scratch (greenfield) since only `.gitignore` and PRD exist in the repository.
- No backend email service is configured yet; `/contacto` will include frontend validation only.
- Logo/isotype is not available; a placeholder hexagon/symbol or text-based brand mark will be used.
- Blog will use placeholder Markdown files; real content will be added later.
- Docker deployment config (`Dockerfile` + static serve) is included in the first slice, but CI/CD pipeline configuration (GitHub Actions, etc.) is deferred.

Please review the questions above. Once confirmed or corrected, this proposal will be finalized and passed to the design phase.
