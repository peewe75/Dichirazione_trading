# Design System Strategy: The Financial Architect

## 1. Overview & Creative North Star
This design system is built upon the Creative North Star of **"The Digital Architect."** In the complex, often volatile world of trader tax reporting, our UI must act as a stabilizing force—an authoritative, structured, and premium environment that mirrors the precision of a high-end architectural blueprint.

We move beyond the "generic fintech" look by rejecting standard grid-locked templates. Instead, we utilize **intentional asymmetry** and **editorial pacing**. This means using expansive white space (breathing room) to separate complex data and overlapping elements to create a sense of tactile depth. The goal is to make the user feel they are interacting with a bespoke concierge service, not just a software tool.

## 2. Colors & Surface Philosophy
The palette balances the deep, authoritative weight of **Professional Navy Blue** (`primary`) with the kinetic energy of **Actionable Bright Blue** (`primary_container`).

### The "No-Line" Rule
To achieve a high-end editorial feel, **1px solid borders are prohibited for sectioning.** We define boundaries through tonal shifts. 
- A hero section using `surface` transitions into a content block using `surface-container-low`. 
- Content importance is signaled by value shifts, not structural lines.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Use the Material tiers to create "nested" depth:
*   **Base Level:** `surface` (#fbf9f8) - The primary canvas.
*   **In-Page Sections:** `surface-container-low` (#f6f3f2) - For secondary content areas.
*   **Priority Cards:** `surface-container-lowest` (#ffffff) - To create a "lifted" appearance of pure white on a warm grey base.

### The "Glass & Gradient" Rule
Floating navigation bars and critical overlays must use **Glassmorphism**. Apply a semi-transparent `surface` color with a `backdrop-blur` of 12px-20px. 
*   **Signature Textures:** For Hero sections or primary CTAs, use a subtle linear gradient from `primary` (#0056be) to `primary_container` (#106eea) at a 135-degree angle. This adds "visual soul" and prevents the flat, clinical look of basic hex codes.

## 3. Typography: Editorial Authority
The type system pairs the geometric precision of **Manrope** for high-impact display with the technical clarity of **Inter** for data-heavy reporting.

*   **Display & Headlines (Manrope):** Used for "The Hook." High-contrast sizing (e.g., `display-lg` at 3.5rem) creates an editorial hierarchy that demands attention and conveys expertise.
*   **Titles & Body (Inter):** Used for "The Fact." Inter provides maximum legibility for the complex terminology of tax law and trading.
*   **Hierarchy Note:** Always maintain a significant scale jump between headlines and body text to avoid a "grey" page. Use `on_surface_variant` (#424754) for body text to reduce eye strain while keeping `on_surface` (#1b1c1c) for bold, authoritative headings.

## 4. Elevation & Depth
Hierarchy is achieved through **Tonal Layering**, not shadows alone.

*   **The Layering Principle:** Place a `surface-container-lowest` card on a `surface-container-low` background. The subtle shift from #f6f3f2 to #ffffff creates a natural, sophisticated lift.
*   **Ambient Shadows:** When a "floating" effect is required (e.g., for a premium pricing tier), use extra-diffused shadows: `box-shadow: 0 20px 40px rgba(0, 86, 190, 0.06)`. Note the use of a `primary` tint in the shadow rather than pure black.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility, use the `outline_variant` token at 20% opacity. **Never use 100% opaque borders.**

## 5. Components

### Service Cards & Trust Signals
*   **Cards:** Forbid divider lines. Separate card headers from content using the **Spacing Scale** (`10` or 2.5rem). Use `surface-container-highest` for small badges or "trust signals" (e.g., "Certified Tax Expert").
*   **Trust Badges:** Render logos of partner brokers or security certifications in a grayscale `outline` color, moving to full color only on hover to maintain a sophisticated, non-cluttered aesthetic.

### Buttons (The Actionable Core)
*   **Primary:** Gradient of `primary` to `primary_container`. Border-radius: `md` (0.375rem). Use `title-sm` for button labels to ensure weight and authority.
*   **Secondary:** Ghost-style. No background, `primary` text, and a `Ghost Border` (outline-variant at 20%).

### Input Fields & Data Entry
*   **Fields:** Use `surface-container-highest` as the background for input fields. This provides a clear "sink" into the page.
*   **States:** On focus, transition the background to `surface_container_lowest` and add a 2px `primary` bottom-border (an architectural "accent" rather than a full box).

### Specialized Components: The Pricing Matrix
*   **Pricing Tables:** Instead of traditional tables, use "The Architect's Grid." Large `display-sm` numbers for the price, surrounded by generous `spacing-16` (4rem) margins. Highlight the "Recommended" tier by shifting its background to `primary` with `on_primary` text, creating a massive focal point.

## 6. Do's and Don'ts

### Do
*   **DO** use asymmetric layouts. If you have an image and text, let the image bleed off the edge of the grid to create a high-end magazine feel.
*   **DO** use `surface-bright` for areas meant to feel "fresh" and "clean."
*   **DO** prioritize typography over icons. The words are the authority; icons are just the accents.

### Don't
*   **DON'T** use black (#000000) for text. Always use `on_surface` or `on_surface_variant` to keep the palette premium and soft.
*   **DON'T** use 1px dividers to separate list items. Use `spacing-4` (1rem) of empty space instead.
*   **DON'T** use standard "drop shadows." If it doesn't look like ambient light, it doesn't belong in this system.