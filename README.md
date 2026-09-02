# Nature's Platter 🥬

A single-page, responsive grocery e-commerce landing page built with **Tailwind CSS** and **Font Awesome** icons.

## Overview

Nature's Platter is a static landing page for an online grocery store, showcasing fresh produce, daily essentials, and promotional offers with a clean, green-accented design.

## Tech Stack

- **HTML5**
- **Tailwind CSS v4** (via CDN — `@tailwindcss/browser`)
- **Font Awesome 7.3.1** (icons, via CDN)

## Structure

| Section | Description |
|---|---|
| **Header** | Logo, desktop nav (Product / Services / Contact us), search & cart icons, Login/Register buttons, and a mobile hamburger menu with a collapsible nav panel |
| **Hero** | Bold headline, supporting copy, and a hero image of fresh produce |
| **Services** | Three feature cards — 24/7 Services, Fast Delivery, Healthy Products |
| **Popular Products** | A green promotional banner (30% off) alongside a responsive grid of 9 product cards (Onion, Tomato, Potato) with ratings and prices |
| **Arrival & Offers** | Two brand promo cards (Daawat, India Gate) with discount call-outs |
| **Newsletter** | Email subscription box overlaid on top of the footer |
| **Footer** | Brand info, navigation links, and social media icons (Facebook, Instagram, X, YouTube) |

## Assets

All images are referenced from a local `./assets/` folder and currently include:

```
assets/
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

> Make sure this folder exists alongside `index.html` with matching filenames, or update the image paths accordingly.

## Responsive Behavior

- **Mobile (< md)**: Hamburger menu toggles a stacked nav panel with full-width Login/Register buttons; Login/Register buttons in the header collapse to icons only.
- **Tablet/Desktop (md and up)**: Full horizontal nav, inline auth buttons, and multi-column grids for services, products, and offers.

## Getting Started

1. Place `index.html` and the `assets/` folder in the same directory.
2. Open `index.html` directly in a browser, or serve it with any static server:
   ```bash
   npx serve .
   ```
3. No build step required — Tailwind and Font Awesome are loaded via CDN.

## Notes

- Product descriptions currently use placeholder **Lorem ipsum** text — replace with real copy before launch.
- Product prices/ratings are static placeholders and should be wired up to real data if this becomes dynamic.
- The mobile menu toggle (`#mobileMenuBtn`) requires a small JS snippet (not included in this file) to actually show/hide `#mobileMenu`.