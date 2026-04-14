# Design System Document

## 1. Overview & Creative North Star: "The Architectural Engine"

The core vision for this design system is **"The Architectural Engine."** We are evolving the developer’s portfolio from a standard web layout into a high-fidelity development environment. It isn't just a website; it’s a peek into the Unity Editor—refined, technical, and premium.

To break the "template" look, we employ **intentional asymmetry**. Hero sections shouldn't be centered; they should feel like a viewport, with typography pushed to the edges to maximize negative space. By utilizing high-contrast typography scales (Space Grotesk for technical precision and Manrope for humanist readability), we create a signature editorial feel that balances cold machine logic with professional warmth. 

The system moves away from "boxes" and toward **layered depth**, using glassmorphism and subtle grid patterns to evoke the sensation of a 3D workspace.

---

## 2. Colors

Our palette is anchored in a monochromatic "Deep Dark" base, punctuated by a hyper-vibrant "Cyber Green" that serves as the lifeblood of the interface.

*   **Primary (`#6bfe9c`):** Use this for high-impact calls to action and critical status indicators. It is the "Active" state of the engine.
*   **Surface Hierarchy:**
    *   **`surface` (`#0d0f0e`):** The absolute floor. Used for the widest backgrounds.
    *   **`surface-container-low` (`#121413`):** For large sectioning.
    *   **`surface-container-highest` (`#242625`):** Reserved for interactive cards and floating panels.
*   **The "No-Line" Rule:** 1px solid borders are strictly prohibited for sectioning. Contrast must be achieved through background shifts. For example, a project gallery section using `surface-container-low` should sit directly against a `surface` background without a stroke.
*   **The "Glass & Gradient" Rule:** Floating navigation or modal overlays must use a 60% opacity version of `surface-container-highest` combined with a `backdrop-blur` of 12px.
*   **Signature Textures:** Apply a subtle `linear-gradient(180deg, primary 0%, primary-container 100%)` to primary buttons and active indicators. This prevents the vibrant green from looking "flat" or "cheap."

---

## 3. Typography

Typography is the "UI of the code." It must feel engineered.

*   **Display & Headline (Space Grotesk):** This is our technical voice. The wide apertures and geometric shapes of Space Grotesk convey a high-tech, modern feel. 
    *   *Application:* Use `display-lg` for hero titles with a `letter-spacing: -0.04em` to create a dense, editorial impact.
*   **Body & Title (Manrope):** This provides the "Human" counterpoint. Manrope's legibility ensures that long-form project descriptions remain readable.
    *   *Application:* Use `body-md` for general descriptions and `title-sm` for small, uppercase labels that act as "Meta-data" for projects.
*   **Visual Hierarchy:** Large, aggressive display sizes paired with significantly smaller, high-contrast labels (`label-md` in `primary`) create an "Information Dashboard" aesthetic rather than a "Standard Page" feel.

---

## 4. Elevation & Depth

We eschew traditional drop shadows for **Tonal Layering**.

*   **The Layering Principle:** Depth is "stacked." An inner element (like a code snippet block) should use `surface-container-lowest` when nested inside a `surface-container-high` card. This creates a "recessed" or "inset" look common in pro-grade IDEs.
*   **Ambient Shadows:** If a floating element (like a mobile menu) requires a shadow, use a 32px blur with 6% opacity using a tinted version of `on-surface`. It should feel like a soft glow rather than a dark stain.
*   **The "Ghost Border" Fallback:** For project cards, if the edge feels lost, use the `outline-variant` token at **15% opacity**. This creates a "hairline" suggestion of a border that only appears when light hits it, mimicking a glass edge.
*   **Subtle Grids:** Backgrounds should feature a repeating 40px dot grid or thin line grid in `outline-variant` at 5% opacity. This reinforces the "Unity Editor" feel.

---

## 5. Components

### Buttons
*   **Primary:** Solid `primary` background. Sharp corners (`DEFAULT: 0.25rem`). Text in `on-primary`. On hover, add a `primary` outer glow (8px blur, 30% opacity).
*   **Secondary/Ghost:** `outline` border at 20% opacity. Text in `on-surface`. No background fill until hover.

### Cards (The "Viewport" Card)
*   **Style:** No borders. Background: `surface-container-highest`. 
*   **Image Handling:** Images should have a 1% `primary` color overlay to unify them with the brand.
*   **Content:** Forbid divider lines. Use `spacing-6` to separate the header from the body text.

### Chips (The "Tag" System)
*   **Action Chips:** Small `label-sm` text. Background: `surface-bright`. Corner radius: `full`.
*   **Selection:** When selected, the chip background becomes `primary-container` with `on-primary-container` text.

### Input Fields
*   **Style:** `surface-container-lowest` background. A bottom-only border using `outline` at 30%. 
*   **Active State:** The bottom border transforms into a 2px `primary` line.

---

## 6. Do's and Don'ts

### Do
*   **Do** use asymmetrical layouts. Place a large headline on the left and a small technical spec list on the far right.
*   **Do** use `backdrop-filter: blur()` on all overlapping elements to maintain the glassmorphism theme.
*   **Do** use the `spacing-20` and `spacing-24` tokens to create massive "breathing room" between major portfolio sections.

### Don't
*   **Don't** use pure white (`#FFFFFF`). Always use `on-surface` (`#f7f6f4`) to keep the "pro" dark-mode aesthetic.
*   **Don't** use standard 1px borders to separate content. It breaks the "Engine" immersion. Use background shifts instead.
*   **Don't** use rounded corners larger than `lg` (0.5rem) for main containers. The system should feel "Engine-precise," not "Mobile-App-bubbly."