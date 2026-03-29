# Design System Document: The Scholarly Editorial

## 1. Overview & Creative North Star
The "Creative North Star" for this system is **The Distinguished Curator**. 

In the Thai educational context, a Performance Agreement (PA) portfolio must balance two worlds: the absolute formality and "trustworthiness" required by administrative standards, and a "modern flair" that demonstrates a teacher’s innovation and digital literacy. 

To break the "template" look, this design system moves away from rigid, boxed grids. Instead, it utilizes **Editorial Asymmetry** and **Tonal Layering**. We treat the portfolio as a high-end academic journal—clean, authoritative, yet breathable. By overlapping elements and using extreme shifts in typography scale (e.g., a very large `display-lg` year next to a small `label-md` caption), we create a visual rhythm that feels bespoke and intentional.

## 2. Colors
Our palette balances the authority of **Navy Blue (`primary`)** with the approachable warmth of **Soft Pink (`secondary`)**.

*   **Primary (Navy):** Used for structural authority and high-level headers. It grounds the design in professionalism.
*   **Secondary (Pink):** Used for accents, highlights, and soft emotional connections. It prevents the portfolio from feeling cold or purely bureaucratic.
*   **The "No-Line" Rule:** 1px solid borders are strictly prohibited for sectioning. Structural boundaries must be defined solely through background shifts. For example, a `surface-container-low` section should sit directly on a `surface` background to define its area.
*   **Surface Hierarchy & Nesting:** Use the tiers to create physical depth.
    *   *Base:* `surface` (#f9f9fb)
    *   *Section Breaks:* `surface-container-low` (#f3f3f5)
    *   *Floating Cards:* `surface-container-lowest` (#ffffff)
*   **The "Glass & Gradient" Rule:** For the Hero section or Profile Cards, apply a subtle linear gradient from `primary` (#001641) to `primary_container` (#00296b) at a 135-degree angle. For floating navigation or modal overlays, use a semi-transparent `surface_container_lowest` with a 12px backdrop-blur to achieve a "frosted glass" editorial look.

## 3. Typography
We utilize a pairing of **Manrope** (Display/Headlines) and **Inter** (Body/Labels). Manrope provides a modern, geometric warmth that feels contemporary, while Inter ensures maximum readability for dense evaluation text.

*   **Display (Manrope):** Use `display-lg` for section numbers (e.g., "01") or large typographic impact statements.
*   **Headlines (Manrope):** Use `headline-md` for PA Criteria titles. The generous x-height of Manrope conveys confidence.
*   **Body (Inter):** Use `body-lg` for the "Teacher’s Reflection" sections. Inter’s neutrality allows the evaluator to focus on the content without visual fatigue.
*   **Labels (Inter):** Use `label-md` in all-caps with a `0.05rem` letter-spacing for metadata, such as "DATE OF ACTIVITY" or "EVIDENCE TYPE."

## 4. Elevation & Depth
In this system, depth is a tool for organization, not just decoration.

*   **The Layering Principle:** To highlight a Certificate in a grid, do not use a border. Place the certificate image on a `surface-container-lowest` card, which sits on a `surface-container-low` section background. This "stacking" creates a natural, soft lift.
*   **Ambient Shadows:** If a "floating" effect is required (e.g., a floating Action Button to "Download PDF"), use an extra-diffused shadow: `offset: 0 10px, blur: 30px, color: rgba(0, 22, 65, 0.05)`. The hint of Navy in the shadow keeps it harmonious with the brand.
*   **The "Ghost Border" Fallback:** If high-contrast separation is needed for accessibility, use the `outline-variant` (#c4c6d2) at **15% opacity**. It should be felt, not seen.
*   **Glassmorphism:** Use for "Photo Gallery" captions. A small overlay using `surface_container_highest` at 70% opacity with a blur allows the image colors to bleed through, making the text feel integrated into the media.

## 5. Components

### Profile Cards
*   **Structure:** Asymmetrical layout. The profile photo should be slightly offset, breaking the top boundary of the card container. 
*   **Style:** Use `surface-container-lowest` for the card body. No borders. Use `primary` for the teacher's name and `secondary` for the "Position/Rank" tag.

### Activity Timelines
*   **Structure:** Avoid the "line with dots" cliché. Use a vertical "ribbon" of `surface-variant`.
*   **Logic:** The year (`display-sm`) sits to the left, while the activity details sit on a `surface-container-low` card to the right. The gap (using `spacing-8`) provides the "modern flair" requested.

### Certificate Grids
*   **Structure:** Tight `spacing-2` between certificates.
*   **Style:** Certificates should have a `0.25rem` (DEFAULT) corner radius. On hover, the card should transition to `surface-container-highest` with a soft ambient shadow. Forbid the use of dividers between items.

### Photo Galleries (Evidence)
*   **Structure:** Masonry-style layout to avoid the "standard grid" look.
*   **Interaction:** Images use `xl` (0.75rem) rounded corners. Captions appear as "Ghost Border" overlays only on interaction.

### Buttons & Inputs
*   **Primary Button:** `primary` (#001641) background with `on_primary` (#ffffff) text. Use `full` rounded corners for a modern, approachable feel.
*   **Secondary Button:** `secondary_fixed` (#ffd9e2) background with `on_secondary_container` (#792b4a) text.
*   **Input Fields:** Use `surface-container-highest` as the fill. The label should be `label-md` in `primary` color. No bottom line; the background fill change is the indicator.

## 6. Do's and Don'ts

### Do
*   **Do** use whitespace as a separator. If two sections feel too close, increase spacing to `spacing-20` or `spacing-24` rather than adding a line.
*   **Do** use `secondary` (Soft Pink) for "Actionable" items or "Success" states to provide a warm, human touch to the evaluation.
*   **Do** use Thai-specific typography adjustments: ensure line-height for Inter/Manrope is set to at least `1.6` to accommodate Thai glyphs and tone marks without clipping.

### Don't
*   **Don't** use pure black (#000000). Always use `on_surface` (#1a1c1d) for text to maintain a premium, editorial feel.
*   **Don't** use standard "drop shadows" with 20%+ opacity. They look "cheap" and dated.
*   **Don't** use more than one "Display" font weight per page. It creates visual noise that detracts from the "Trustworthy" goal.