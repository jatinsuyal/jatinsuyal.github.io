# Design System Strategy: The Immersive Engine

## 1. Overview & Creative North Star
**Creative North Star: "The HUD of High-Fidelity"**

This design system is not a website; it is an interface into a high-performance engine. Moving away from the static, "templated" grid of typical portfolios, this system treats the browser as a viewport. We prioritize **Intentional Asymmetry** and **Tonal Depth** to mimic the complexity of a game engine’s UI (like Unity’s Editor or a Triple-A game’s HUD), while maintaining the high-end editorial polish of a luxury tech brand.

By overlapping elements and using a "stacking" logic, we break the horizontal-strip layout. Hero sections should feel like a splash screen, where typography is large, aggressive, and partially obscured by high-quality game renders, creating a sense of three-dimensional space.

---

## 2. Colors & Surface Logic

### The Palette
The core of this system lies in the tension between the void of the background and the radioactive energy of the accents.
- **Surface & Depth:** We utilize `#0e0e0e` as our true-dark foundation.
- **Neon Accents:** `Primary (#81ecff)` provides a surgical, high-tech feel, while `Secondary (#c3f400)` acts as a disruptive, high-energy call-to-action.

### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid borders to define sections. Sectioning is achieved through color-blocking with the surface hierarchy. 
- Use a `surface-container-low (#131313)` section to house a grid of cards, sitting atop the `background (#0e0e0e)`.
- Physical boundaries are "felt" through value shifts, not drawn with lines.

### Surface Hierarchy & Nesting
Treat the UI as a series of nested physical layers.
- **Level 0 (Background):** `surface-dim (#0e0e0e)` — The infinite void.
- **Level 1 (Sections):** `surface-container-low (#131313)` — Subtle structural shifts.
- **Level 2 (Cards/Modules):** `surface-container (#1a1a1a)` — The interactive "plates."
- **Level 3 (Floating HUDs):** `surface-bright (#2c2c2c)` — For high-priority modals or tooltips.

### The "Glass & Gradient" Rule
To achieve "Game/Tech" immersion, use Glassmorphism for floating UI elements.
- **Token Usage:** Use `surface-container` at 60% opacity with a `20px` backdrop-blur. 
- **Signature Texture:** Apply a linear gradient from `primary` to `primary-container` on high-value CTAs. This creates a "backlit" effect common in high-end gaming hardware.

---

## 3. Typography: Editorial Kineticism

We use a high-contrast scale where display text is massive and structural, while body text is surgically clean.

- **Display (Space Grotesk):** This is our "Machinery" font. Use `display-lg (3.5rem)` with tight letter-spacing (-0.02em) for project titles. It should feel heavy, industrial, and authoritative.
- **Headline & Title (Space Grotesk/Manrope):** Use `headline-lg` for section markers. Pair these with `title-md` in `on-surface-variant` for sub-headers to create a clear "File Metadata" aesthetic.
- **Body (Manrope):** All descriptive text must use Manrope. It provides a humanistic balance to the cold, tech-heavy headings. Maintain a generous line-height (1.6) for readability against the dark background.
- **Labels (Inter):** Reserved for technical data (e.g., "ENGINE: UNITY", "FPS: 60"). Use `label-md` in all-caps with `0.1rem` letter-spacing.

---

## 4. Elevation & Depth

### The Layering Principle
Depth is achieved by stacking. A `surface-container-highest (#262626)` element should only exist inside a `surface-container-low` parent. This "inner-glow" or "inner-shadow" logic makes the UI feel like it has been machined out of a single block of charcoal.

### Ambient Shadows & Neon Glows
- **Shadows:** Avoid black shadows. Use a diffused shadow (`blur: 40px`) using a 4% opacity of the `primary` color to simulate ambient light reflecting off a neon source.
- **The "Ghost Border" Fallback:** If a container needs more definition, use the `outline-variant (#484847)` at **15% opacity**. It should be a suggestion of an edge, not a hard stop.
- **Glowing Borders:** For hovered states on game cards, use a `1px` border with a linear gradient of `primary` to `transparent`. This mimics the "selection" state in a game engine.

---

## 5. Components

### The "Game Card" (High-End Editorial)
*Forbid the use of divider lines.* Use vertical white space (`spacing-8`) to separate the image from the metadata.
- **Structure:** A full-bleed image container with `rounded-md`.
- **Overlay:** A subtle `surface-container-lowest` gradient at the bottom to house the title.
- **Interaction:** On hover, the image scales slightly (1.05x) and the "Ghost Border" increases in opacity to 40% with a `primary` glow.

### Interactive HUD Buttons
- **Primary:** `primary` background with `on-primary` text. No rounded corners—use `rounded-sm` for a sharp, precision look.
- **Tertiary (The "Data" Button):** Transparent background, `label-md` text, and a `primary` underline that only spans 30% of the button width, expanding to 100% on hover.

### Progress & Skill Meters
- Instead of standard bars, use a series of small, segmented blocks using the `spacing-0.5` scale. Filled blocks use `secondary`, empty blocks use `surface-variant`.

### Technical Tooltips
- Background: `surface-bright` with 80% opacity.
- Border: `primary` at 20% opacity.
- Animation: Slide up 4px with a quick "glitch" or snap ease-out.

---

## 6. Do’s and Don'ts

### Do:
- **Do** use `secondary (#c3f400)` sparingly. It is a "System Warning" or "High Priority" color. If everything is neon, nothing is neon.
- **Do** use asymmetrical margins. Offsetting a text block by `spacing-12` relative to its header creates a sophisticated, non-linear feel.
- **Do** lean into `on-surface-variant` for secondary information to maintain a high-contrast ratio for the primary content.

### Don't:
- **Don't** use standard `drop-shadow`. If an element needs to float, use tonal shifting and backdrop blurs.
- **Don't** use pure white (#FFFFFF) for long-form body text. Use `on-surface` (which is slightly muted) to prevent "halogen-light" eye strain on dark backgrounds.
- **Don't** use `rounded-full` for anything other than status indicators. We want the "Gaming/Tech" aesthetic to feel architectural and sharp, not bubbly.