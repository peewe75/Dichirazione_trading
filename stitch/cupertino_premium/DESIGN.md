# Design System Specification: High-End Editorial

## 1. Overview & Creative North Star
The **Creative North Star** for this design system is **"The Digital Curator."** 

Moving beyond a standard tech-minimalist framework, this system treats the interface as a premium editorial gallery. It is characterized by an uncompromising commitment to whitespace, high-fidelity imagery, and a "content-first" hierarchy. We reject the "boxed-in" nature of traditional web grids in favor of **Intentional Asymmetry**. By utilizing significant vertical breathing room and large-scale typography, we create a rhythmic experience that feels less like a software application and more like a high-end physical publication. Every element must feel intentional, unhurried, and precise.

## 2. Colors
Our palette is rooted in sophisticated neutrals, using a deep monochromatic core with a single vibrant accent for high-utility interactions.

*   **Primary Accent (`#0058bc`):** Reserved strictly for primary calls to action and critical interactive states.
*   **Neutral Core (`#1D1D1F`, `#f9f9fb`):** The foundation of our "Ink on Paper" high-contrast feel.
*   **The "No-Line" Rule:** We explicitly prohibit the use of 1px solid borders for sectioning or containment. Boundaries are defined exclusively through background color shifts. Use `surface-container-low` (`#f3f3f5`) against a `background` (`#f9f9fb`) to indicate a change in context.
*   **Surface Hierarchy & Nesting:** Treat the UI as layers of fine material. To create depth, nest containers using tiers: 
    *   Base: `surface` (`#f9f9fb`)
    *   Secondary Depth: `surface-container-low` (`#f3f3f5`)
    *   Prominent Content: `surface-container-highest` (`#e2e2e4`)
*   **The "Glass & Gradient" Rule:** To achieve a premium "Signature" look, use Backdrop Blurs (20px+) with semi-transparent surface colors (e.g., `on-surface` at 5% opacity). For primary Hero CTAs, use a subtle linear gradient from `primary` (`#0058bc`) to `primary-container` (`#0070eb`) at a 145-degree angle to provide tonal depth and "soul."

## 3. Typography
Typography is the primary architecture of this system. We use **Inter** (as the web-standard equivalent to SF Pro) to maintain a clean, modernist aesthetic.

*   **Display Scales (lg/md/sm):** Used for "Billboard" moments. These should use tight letter-spacing (-0.02em) to feel authoritative and architectural.
*   **Headline & Title Scales:** Convey the brand's voice. High-contrast sizing between Headlines (`2rem`) and Body text (`1rem`) is required to create a clear editorial "entry point" for the eye.
*   **Body Text:** Optimized for long-form reading. Use `body-lg` (16px) for standard descriptions and `body-md` (14px) for secondary metadata.
*   **Label Scales:** Used sparingly for micro-copy and eyebrow headers. Always in uppercase with slightly increased tracking (+0.05em) when used as an eyebrow header.

## 4. Elevation & Depth
We eschew "Material" style drop shadows for **Tonal Layering** and **Ambient Light.**

*   **The Layering Principle:** Place a `surface-container-lowest` (#ffffff) card on a `surface-container-low` (#f3f3f5) background. This creates a soft, natural "lift" that mimics white paper on a light grey desk.
*   **Ambient Shadows:** For floating elements (like Modals or Floating Nav), use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(26, 28, 29, 0.06);`. The shadow must feel like a soft glow of occlusion, not a dark smudge.
*   **The "Ghost Border":** If a container requires further definition (e.g., on a high-motion background), use the `outline-variant` token at **15% opacity**. Never use a 100% opaque border.
*   **Glassmorphism:** Apply `backdrop-filter: blur(25px)` to headers and floating panels to allow background colors to bleed through, softening the edges of the UI and integrating it with the underlying content.

## 5. Components

### Buttons
*   **Primary:** High-gloss. Uses the `primary` to `primary-container` gradient. Roundedness: `full`. No border.
*   **Secondary:** Ghost style. Uses a `primary` label on a transparent background, or a `secondary-container` background with `on-secondary-container` text.
*   **Interaction:** On hover, apply a subtle scale-up (1.02) rather than a drastic color change.

### Cards & Lists
*   **Rule:** Forbid divider lines.
*   **Cards:** Use `surface-container-low` with a `lg` (1rem) corner radius. Vertical separation between list items should use the `spacing.6` (2rem) scale to allow the content to breathe.
*   **Images in Cards:** Always use a subtle `inner-glow` or `inset-shadow` on image containers to ensure they feel seated within the UI.

### Input Fields
*   **Visual Style:** Minimalist underline or subtle `surface-container-high` background.
*   **Focus State:** A 2px glow of `surface-tint` at 30% opacity. No harsh black outlines.
*   **Error State:** Use `error` text (`#ba1a1a`) with a `error-container` background wash.

### Chips & Badges
*   **Styling:** Use `secondary-fixed` with `label-md` typography. Keep padding generous (e.g., `spacing.2` vertical, `spacing.4` horizontal).

## 6. Do's and Don'ts

### Do:
*   **Use Asymmetric Padding:** Align text to the left but allow imagery to bleed to the edge of the container to create visual interest.
*   **Embrace Negative Space:** If a section feels "busy," increase the vertical spacing to `spacing.20` (7rem).
*   **Micro-Interactions:** Use slow, "physics-based" transitions (e.g., 400ms ease-out) for all state changes.

### Don't:
*   **Don't use Dividers:** Never use a horizontal rule `<hr>` to separate content. Use a background color shift or `spacing.12`.
*   **Don't use Pure Black:** Use `on-surface` (`#1a1c1d`) for text; it is softer and more premium than `#000000`.
*   **Don't Over-Decorate:** If a design element doesn't serve a functional or clear editorial purpose, remove it. The content is the decoration.
*   **Don't use Small Radii:** Avoid the "boxy" look. Use `md` (0.75rem) or `lg` (1rem) for most containers to maintain a friendly yet sophisticated feel.