# Nature's Platter — Grocery Landing Page

A single-page, mobile-first grocery e-commerce landing page built with static HTML, Tailwind CSS (CDN), and Font Awesome icons.

## Tech Stack

| Tool | Source | Purpose |
|---|---|---|
| Tailwind CSS v4 | `cdn.jsdelivr.net/npm/@tailwindcss/browser@4` | Utility-first styling, no build step required |
| Font Awesome 7.3.1 | `cdnjs.cloudflare.com` | Icons (search, cart, hamburger, social) |
| Vanilla JS | inline `<script>` | Mobile menu toggle only |

No build tools, bundlers, or package managers are required — the page runs by opening `index.html` directly or serving the folder with any static file server.

## Project Structure

```
natures-platter/
├── index.html          # Full single-page site
├── README.md            # This file
└── assets/               # Referenced images (not included — see below)
    ├── nav-logo.png
    ├── footer-logo.png
    ├── Hero Section 1.png
    ├── service.png
    ├── delivery.png
    ├── products.png
    ├── popular.png
    ├── onion.png
    ├── tomato.png
    ├── potato.png
    ├── dawat-logo.png
    ├── offers-1.png
    ├── gate-logo.png
    ├── offers-2.png
    └── grocery-basket.png
```

> `index.html` references all images via relative `./assets/...` paths. Place the actual image files in an `assets/` folder next to `index.html` for the page to render correctly.

## Page Sections

1. **Header** — logo, desktop nav (Product / Services / Contact us), search & cart icons, Login/Register buttons, and a hamburger menu for mobile.
2. **Hero** — headline, subtext, and hero image.
3. **Services** — 3 feature cards (24/7 Services, Fast Delivery, Healthy Products).
4. **Popular Products** — a 30%-off promo banner plus a 9-item product grid (Onion, Tomato, Potato).
5. **Arrival & Offers** — two brand promo banners (DAAWAT, INDIA GATE).
6. **Newsletter** — email signup box that overlaps the footer on desktop.
7. **Footer** — brand blurb, nav links, and social icons.

## Mobile Optimization Notes

The page is responsive from small phones up through desktop using Tailwind's `sm:` / `md:` / `lg:` breakpoints:

- **Header**: desktop nav links are hidden below `md`; a hamburger button (`#mobileMenuBtn`) toggles a slide-down mobile nav panel (`#mobileMenu`) containing the same links plus Login/Register. Login/Register buttons in the top bar are hidden below `sm` to avoid crowding and are available inside the mobile panel instead.
- **Typography & spacing**: heading sizes, section padding, and gaps step down at each breakpoint (e.g. `text-3xl sm:text-4xl md:text-5xl`, `py-10 sm:py-16`) instead of using one fixed desktop size everywhere.
- **Promo banner** (30% off): `min-h` scales down (`min-h-[260px] sm:min-h-[320px] lg:min-h-[380px]`) so it doesn't force excess scroll height on small screens.
- **Arrival & Offers cards**: switch from `flex-row` to `flex-col` below `sm` so the logo/text block and product image stack instead of getting squeezed side-by-side.
- **Newsletter box**: the negative-margin overlap with the footer (`-mb-24`) is desktop-only (`md:-mb-24`); on mobile it sits inline with normal spacing (`mb-8`) so it doesn't overlap or clip the footer content. Footer top padding follows the same pattern (`pt-10 md:pt-36`).
- **Images**: basket and offer-pack images get smaller `max-w` / `max-h` caps on mobile so they don't dominate the viewport.

## Fixes Applied

- Added missing mobile navigation (hamburger + toggle script) — the original desktop nav had no mobile equivalent, so Product/Services/Contact links were unreachable on small screens.
- Corrected a leftover pet-store copy mismatch: the footer tagline and the promo banner text referenced "furry friends" / were cut off mid-sentence, inconsistent with a grocery site. Footer copy was corrected to grocery-appropriate wording.
- Reviewed and corrected `<!-- -->` comments throughout so each one accurately labels the section or card it precedes (e.g. per-product comments now name the actual product instead of a generic placeholder).

## Known Content Note

The 30%-off promo banner's paragraph ("Discover a world of treats, toys, and essentials handpicked for") is still a truncated/mismatched sentence carried over from the original markup — it reads like leftover pet-store copy and is cut off. It hasn't been rewritten since it's marketing copy rather than a structural or comment issue; consider updating it separately with real grocery-store promo text.

## Running Locally

```bash
# any static server works, e.g.:
npx serve .
# or
python3 -m http.server 8080
```

Then open `http://localhost:8080` (or the port shown).