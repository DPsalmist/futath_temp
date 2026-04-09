# Design System Document: FUTA Teaching Hospital

## 1. Overview & Creative North Star: "The Clinical Sanctuary"
The digital presence of a teaching hospital must bridge the gap between rigorous academic authority and empathetic patient care. This design system departs from the "utilitarian" medical template to embrace **The Clinical Sanctuary**—a creative north star that prioritizes clarity, breathability, and quiet confidence.

By utilizing intentional asymmetry and "White Space as a Structure," we move away from boxed-in layouts. The system leverages high-contrast editorial typography (Manrope) and deep tonal layering to create an environment that feels less like a software interface and more like a premium, high-end medical journal.

---

## 2. Colors & Tonal Depth
This system rejects the "flat" web. We use a sophisticated palette to create a sense of physical space and authoritative depth.

### The "No-Line" Rule
**Explicit Instruction:** 1px solid borders are prohibited for sectioning content. Boundaries must be defined through background color shifts or subtle tonal transitions. A `surface-container-low` section sitting on a `surface` background is the standard for separation.

### Surface Hierarchy & Nesting
Instead of a flat grid, treat the UI as stacked sheets of fine vellum.
- **Base Layer:** `surface` (#f9f9f9) or `surface-container-lowest` (#ffffff).
- **Secondary Layer:** `surface-container-low` (#f3f3f4) for subtle grouping.
- **Top Layer:** `surface-container-highest` (#e2e2e2) for high-emphasis interactive areas.

### The "Glass & Gradient" Rule
To elevate the hospital's digital touchpoints:
- **Glassmorphism:** Use `surface` colors at 80% opacity with a `24px` backdrop blur for navigation bars and floating modals.
- **Signature Gradients:** For Hero backgrounds and Primary CTAs, use a linear gradient: `primary` (#00263f) to `primary-container` (#0b3c5d) at 135 degrees. This adds "soul" and prevents the medical blue from feeling sterile.

---

## 3. Typography: The Editorial Voice
We use two distinct sans-serif families to balance modern tech with institutional trust.

*   **Display & Headlines (Manrope):** Chosen for its geometric precision and modern "tech-forward" feel. Use `display-lg` and `headline-lg` with tight letter spacing (-0.02em) to command authority in headers.
*   **Body & Labels (Public Sans):** A neutral, highly legible face designed for clarity in dense medical documentation.

| Token | Font | Size | Weight | Role |
| :--- | :--- | :--- | :--- | :--- |
| `display-lg` | Manrope | 3.5rem | 700 | Hero Statements |
| `headline-md` | Manrope | 1.75rem | 600 | Section Headers |
| `title-md` | Public Sans | 1.125rem | 600 | Sub-headers / Card Titles |
| `body-md` | Public Sans | 0.875rem | 400 | General Content |
| `label-md` | Public Sans | 0.75rem | 500 | Metadata / Small Caps |

---

## 4. Elevation & Depth: Tonal Layering
Traditional drop shadows are often messy in medical contexts. We use **Tonal Layering** to create hierarchy.

*   **The Layering Principle:** To lift a card, do not add a shadow. Instead, place a `surface-container-lowest` (#ffffff) card on top of a `surface-container-low` (#f3f3f4) background.
*   **Ambient Shadows:** For floating elements (e.g., FABs, floating headers), use a diffused, low-opacity shadow: `box-shadow: 0 12px 32px rgba(11, 60, 93, 0.06)`. Note the use of the Navy Blue (`primary-container`) in the shadow tint to maintain color harmony.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility, use `outline-variant` (#c2c7ce) at **15% opacity**. Never use 100% opaque lines.

---

## 5. Components

### Buttons
*   **Primary:** Gradient of `primary` to `primary-container`. `lg` (0.5rem) roundedness. No border.
*   **Secondary:** Solid `secondary-container` (#d5e4f6) with `on-secondary-container` (#576675) text.
*   **Tertiary:** Ghost style. No background. `primary` text. High-contrast hover state using `surface-container-high`.

### Cards & Lists
*   **Rule:** Forbid the use of divider lines.
*   **Separation:** Use `24px` of vertical white space or a change from `surface` to `surface-container-low`.
*   **Interaction:** On hover, a card should shift from `surface-container-lowest` to a subtle `primary-fixed` tint to signal interactivity.

### Input Fields
*   **Style:** Minimalist. No bottom border. Instead, use a filled style with `surface-container-high` and `sm` (0.125rem) roundedness at the bottom only.
*   **Focus State:** The label (Public Sans) should animate to a smaller `label-sm` above the input, changing color to `tertiary` (Teal).

### Medical-Specific Components
*   **Status Badges:** Use `tertiary-fixed` (#a4eeff) with `on-tertiary-fixed-variant` (#004e5a) for "Available" states. Use `error-container` for "Urgent."
*   **Patient Progress Trackers:** Use thick `8px` bars with `lg` roundedness. The background track should be `surface-variant` with the progress filled in the Primary-to-Teal gradient.

---

## 6. Do’s and Don’ts

### Do
*   **Do** use asymmetrical layouts for Hero sections (e.g., text left-aligned, imagery overlapping the container edge).
*   **Do** use `tertiary` (#00282e / Teal) sparingly as an "action accent"—only for calls to action or vital status indicators.
*   **Do** prioritize "Breathing Room." If an element feels crowded, double the white space.

### Don't
*   **Don't** use pure black (#000000) for text. Use `on-surface` (#1a1c1c) to keep the aesthetic premium.
*   **Don't** use standard "Material Design" cards with heavy shadows. This system relies on background color shifts.
*   **Don't** use 1px dividers to separate list items; use `8px` of empty space and subtle hover backgrounds instead.
*   **Don't** use sharp 0px corners. Always use at least `sm` (0.125rem) or `md` (0.375rem) roundedness to keep the medical environment feeling approachable.