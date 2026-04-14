# Design System Specification: Technical Immersive Portfolio

## 1. Overview & Creative North Star: "The Master Console"
The North Star for this design system is **The Master Console**. We are not building a website; we are designing a high-end, proprietary workstation interface used by a lead technical architect at a AAA studio. 

To move beyond the "template" look, this system rejects traditional web layouts in favor of **Technical Asymmetry**. Elements should feel like HUD (Heads-Up Display) modules—floating, precise, and data-rich. We achieve "Infinite Depth" through complex tonal layering and glassmorphic translucency, creating a UI that feels like it exists within a three-dimensional light-box.

### Core Principles:
*   **Technical Authority:** Every pixel must feel intentional. Use thin, precise strokes and monospaced-adjacent scales.
*   **Immersive Depth:** Layouts should feel like stacked panes of glass.
*   **Pulse & Feedback:** Interactivity is signaled by "Pulse Blue" (#00D1FF) glows and micro-animations.

---

## 2. Colors & Surface Architecture
The palette is rooted in `background` (#131313) to simulate a darkened studio environment. We use "Pulse Blue" as our primary interactive beacon.

### The "No-Line" Rule
Traditional 1px solid borders for sectioning are strictly prohibited. Boundaries must be defined through:
1.  **Background Shifts:** Transitioning from `surface` to `surface-container-low`.
2.  **Tonal Transitions:** Using `surface-container-highest` for high-priority modules against a `surface-dim` background.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Nesting is the primary tool for hierarchy:
*   **Base Level:** `surface` (#131313) for the main canvas.
*   **Level 01 (Layout Blocks):** `surface-container-low` (#1c1b1b) for large content areas.
*   **Level 02 (Interactive Modules):** `surface-container-high` (#2a2a2a) for cards or code snippets.
*   **Level 03 (Floating HUDs):** `surface-container-highest` (#353534) with 80% opacity and `backdrop-filter: blur(12px)`.

### The "Glass & Gradient" Rule
To elevate beyond flat design, all primary CTAs and hero headers should utilize a subtle linear gradient from `primary` (#a4e6ff) to `primary-container` (#00d1ff) at a 135-degree angle. This provides a "lit-from-within" tech aesthetic.

---

## 3. Typography
We utilize a high-contrast pairing to balance technical precision with human readability.

*   **Technical Headers (Space Grotesk):** Chosen for its geometric, futuristic construction. All `display` and `headline` tiers should use a `letter-spacing` of `-0.02em` to feel like high-end hardware branding.
*   **Operational Text (Manrope):** Chosen for its exceptional legibility at small scales. All `body` and `title` tiers use Manrope to ground the technicality in professional editorial clarity.

**Hierarchy Role:**
*   **Display/Headline:** For project titles and "Mission Critical" statements.
*   **Label-sm/md:** Use exclusively for metadata, terminal-style timestamps, and technical specs. Always uppercase with `0.1rem` tracking.

---

## 4. Elevation & Depth: Tonal Layering
We do not use shadows to represent "elevation" in the traditional sense; we use **Luminance and Blur**.

*   **The Layering Principle:** Place a `surface-container-lowest` card on a `surface-container-low` section to create a "recessed" effect. Conversely, place `surface-container-highest` on `surface` to "lift" the element.
*   **Ambient Shadows:** For floating HUD elements, use a highly diffused shadow: `box-shadow: 0 20px 50px rgba(0, 209, 255, 0.04)`. Note the tint: shadows should be a faint version of our `primary` pulse, not black.
*   **The "Ghost Border":** Where containment is required (e.g., input fields), use the `outline-variant` token at **15% opacity**. High-contrast, 100% opaque borders are forbidden as they "flatten" the immersive depth.
*   **Glassmorphism:** Navigation bars and detail panels must use `surface-variant` with a 60% alpha channel and a heavy `backdrop-filter: blur(20px)`. This integrates the UI into the background content.

---

## 5. Components

### Buttons (The "Activation" Units)
*   **Primary:** Gradient fill (`primary` to `primary-container`). Corner radius: `0px`. Text: `label-md` uppercase. On hover: Add a `0 0 15px #00D1FF` outer glow.
*   **Secondary:** Ghost style. `outline-variant` at 20% opacity. On hover: Background shifts to `surface-container-highest`.
*   **Tertiary:** No border or background. Underlined with a 1px `primary` stroke on hover only.

### Cards & Modules
*   **Forbid Dividers:** Do not use lines to separate content. Use a `1.75rem` (8) or `2.25rem` (10) vertical gap.
*   **The "Data-Corner":** Add a single 4px vertical accent of `primary` in the top-left corner of cards to denote "Active Systems."

### Inputs & Terminal Fields
*   **Styling:** `surface-container-lowest` background. 0px border-radius. Use `label-sm` for the floating label, always in `primary` color to simulate a console prompt.
*   **Micro-interaction:** On focus, the bottom border "grows" from the center using the `primary` token.

### Additional Component: "The Status Bar"
A persistent `surface-container-highest` bar (80% opacity) at the very top or bottom of the screen. It displays technical metadata: current build version, "System Status: Nominal," and local coordinates. Use `label-sm` for all text here.

---

## 6. Do's and Don'ts

### Do:
*   **Embrace Asymmetry:** Align some text to the far left and metadata to the far right to create a "wide-screen console" feel.
*   **Use the Spacing Scale:** Stick strictly to the `0.2rem` (1) increments to maintain a technical "grid-locked" appearance.
*   **Layer Surfaces:** Use at least three tiers of `surface-container` in every complex view to ensure depth.

### Don't:
*   **Don't use Rounded Corners:** Every `borderRadius` token is `0px`. Roundness suggests consumer-grade software; sharp edges suggest professional-grade tools.
*   **Don't use Default Shadows:** Never use `rgba(0,0,0,0.5)`. Shadows must be low-opacity and tinted by the `primary` or `on-surface` color.
*   **Don't use Solid Lines:** Avoid horizontal rules (`<hr>`). Use space or a change in `surface` color to separate concepts.