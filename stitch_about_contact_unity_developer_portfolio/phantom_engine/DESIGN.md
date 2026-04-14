# Design System Strategy: AAA Engine Tooling

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Architect’s Console."** 

This system rejects the "web-as-a-document" paradigm. Instead, it treats the interface as a high-performance IDE or a world-building engine. It is designed to feel like a heavy, professional instrument—precise, industrial, and deeply technical. We break the "template" look by utilizing a rigid, mathematical grid that is interrupted by intentional, high-fidelity overlays and 3D depth. 

While the layout is grounded in a 12-column grid, we achieve a "signature" feel through **Mechanical Asymmetry**: using large `display-lg` typography to anchor the eye, while placing technical `label-sm` metadata in unexpected, peripheral locations (like the edges of the viewport) to mimic a diagnostic head-up display (HUD).

## 2. Colors: Phantom & Carbon
The palette is rooted in the deep `Carbon Grey` (`surface-dim`) and energized by the high-frequency `Phantom Blue` (`primary`).

### The "No-Line" Rule
Sectioning must never be achieved via 1px solid borders. Boundaries are defined strictly through **Background Shift**.
*   **The Foundation:** Use `surface` (#131313) for the base layer.
*   **The Content Block:** Use `surface-container-low` (#1c1b1b) to define large content areas.
*   **The Contrast:** Transition to `surface-container-high` (#2a2a2a) to draw focus without a single line stroke.

### Surface Hierarchy & Nesting
Think of the UI as a physical stack of carbon-fiber and glass plates.
1.  **Bottom Layer (Viewport):** `surface-container-lowest` (#0e0e0e).
2.  **Mid Layer (Workspace):** `surface-container` (#201f1f).
3.  **Top Layer (Active Tooling):** `surface-container-highest` (#353534).

### The "Glass & Gradient" Rule
To elevate the "Phantom Blue" from a flat color to a light source, use subtle linear gradients. 
*   **Main CTAs:** Transition from `primary` (#98cbff) at the top-left to `primary_container` (#00a3ff) at the bottom-right at a 135° angle.
*   **Glassmorphism:** For floating diagnostic panels, use `surface_variant` at 40% opacity with a `20px` backdrop-blur. This allows the "world" underneath to bleed through, maintaining the software-engine vibe.

## 3. Typography: Technical Authority
We pair the aggressive, geometric terminals of **Space Grotesk** with the utilitarian precision of **Manrope**.

*   **Display & Headlines (Space Grotesk):** Used for "Hard Data." High tracking (letter-spacing) on `headline-sm` and tight tracking on `display-lg` creates a cinematic contrast.
*   **Body (Manrope):** Used for "Documentation." Manrope provides the readability required for technical logs and deep-dives.
*   **Technical Labels (Space Grotesk):** All `label-md` and `label-sm` should be set in Uppercase. This mimics the labeling found on physical hardware and engine viewports.

## 4. Elevation & Depth: Tonal Layering
Traditional shadows are prohibited. Depth is a result of light physics within the engine.

*   **The Layering Principle:** A "Card" is not a box with a shadow; it is a `surface-container-low` shape sitting on a `surface` background. The depth is felt through the color value shift.
*   **Ambient Shadows:** For high-priority floating modals, use a custom shadow: `0px 24px 48px rgba(0, 163, 255, 0.06)`. This subtle "Phantom Blue" tint suggests the element is emitting light onto the surface below.
*   **The "Ghost Border" Fallback:** If a tactile edge is required (e.g., an input field), use `outline_variant` (#3f4852) at **15% opacity**. This creates a "hairline" effect that looks like etched glass rather than a drawn line.

## 5. Components: The Tooling Kit

### Buttons (The "Actuator")
*   **Primary:** Gradient fill (Primary to Primary-Container), `rounded-sm` (0.125rem). No border. On hover: Increase `surface-tint` glow.
*   **Secondary:** Ghost Border (15% opacity `outline`). Text in `on-surface`.
*   **Tertiary:** All-caps `label-md` with a leading `0.5` spacing icon.

### Input Fields (The "Parameter Entry")
*   **Style:** `surface-container-lowest` background with a bottom-only "Ghost Border".
*   **Focus State:** The bottom border transforms into a 2px `primary_container` line. Use `label-sm` as a floating label that never leaves the "Technical Accents" style.

### Cards & Lists (The "Data Nodes")
*   **Rule:** Forbid divider lines. 
*   **Structure:** Use `spacing-8` (1.75rem) to separate list items. Use a `surface-container-high` background on hover to indicate selection.

### Tactical Components
*   **Node Connectors:** Vertical/Horizontal 1px `outline_variant` lines at 10% opacity to show parent-child relationships in lists.
*   **Status Blips:** Small circular indicators using `tertiary` (#ffb77d) for "Warning" and `primary` (#98cbff) for "Active/Running."

## 6. Do’s and Don’ts

### Do:
*   **Do** use `spacing-px` and `spacing-0.5` for microscopic alignment of technical labels.
*   **Do** use `Space Grotesk` for all numerical data. It looks like a readout.
*   **Do** apply `rounded-sm` (0.25rem) to almost everything. Rigid corners feel professional; overly rounded corners feel "consumer-grade."

### Don’t:
*   **Don’t** use pure white (#FFFFFF). Always use `on-surface` (#e5e2e1) to maintain the dark-room engine atmosphere.
*   **Don’t** use standard "drop shadows." If it doesn't look like it’s being lit by the "Phantom Blue" light source, remove it.
*   **Don’t** use center-alignment for long-form text. Software is left-aligned and systematic. Use center-alignment only for `display-lg` hero moments.