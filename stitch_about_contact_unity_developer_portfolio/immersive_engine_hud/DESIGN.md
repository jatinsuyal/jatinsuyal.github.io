# Design System: The Immersive Engine HUD

## 1. Overview & Creative North Star

### Creative North Star: "The Immersive Engine HUD"
This design system is not a website; it is a high-performance terminal interface for a Senior Unity Developer. It moves away from the "web-page" paradigm toward a functional, data-rich environment that feels like an integrated development tool (IDE) or a futuristic cockpit.

To achieve this, the design system utilizes **Atmospheric Brutalism**. We break the standard "centered container" layout in favor of intentional asymmetry, technical data-readouts, and edge-to-edge utility. The interface should feel "live," utilizing grid overlays and scanline textures to suggest a persistent, real-time calculation engine running beneath the surface.

## 2. Colors & Surface Logic

The palette is rooted in the void—a deep, obsidian-like environment (`surface-dim` #131315) punctuated by high-energy plasma (`primary-container` #00E5FF) and toxic-reactive agents (`secondary-container` #CCFF00).

### The "No-Line" Rule
Traditional 1px solid decorative borders are strictly prohibited for sectioning. Boundaries must be defined through:
1.  **Tonal Shifts**: Use `surface-container-low` for large sections and `surface-container-high` for interactive panels.
2.  **Structural Grid Overlays**: Instead of a border, use a repeating 24px grid pattern (opacity 5%) to define the workspace.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked, light-emitting panels.
*   **Base Layer**: `surface` (#131315) – The background void.
*   **Primary Workspaces**: `surface-container-low` – Used for large content blocks.
*   **Floating HUD Elements**: `surface-container-highest` with a `backdrop-blur` of 12px and 60% opacity. This creates the "Glassmorphism" effect, allowing the grid and scanlines to bleed through.

### Signature Textures
*   **The Scanline Pulse**: A subtle, top-to-bottom linear gradient overlay at 2% opacity to simulate a CRT refresh.
*   **Glow States**: Interactive elements do not just change color; they emit a `primary-fixed-dim` shadow with a 15px blur to simulate neon light projection.

## 3. Typography

The typographic strategy balances "The Machine" (Space Grotesk) with "The Human" (Manrope).

*   **The Technical Lead (Space Grotesk)**: Used for all `display`, `headline`, and `label` roles. Its idiosyncratic terminals and geometric construction evoke mid-century radar tech and modern code editors.
*   **The Clarity Layer (Manrope)**: Used for `title` and `body` roles. It provides high legibility for long-form technical documentation or project descriptions.

**Hierarchy Tip:** Always use `label-sm` in all-caps with 0.1em letter spacing for metadata (e.g., "SYSTEM_STATUS // ACTIVE").

## 4. Elevation & Depth

In a HUD, depth is not created by sunlight (drop shadows), but by **optical layering and light emission**.

### The Layering Principle
Stacking must follow a strict luminosity logic. Placing a `surface-container-highest` card on a `surface` background creates an immediate visual "pop." Use `surface-container-lowest` for "cut-out" areas like input fields to make them feel recessed into the hardware.

### Ambient Glows
For floating "High-Priority" modals, avoid black shadows. Instead, use:
*   **Shadow Color**: `primary` (#C3F5FF)
*   **Opacity**: 10%
*   **Blur**: 40px
This simulates the light of a holographic projection hitting the background.

### The "Ghost Border" Fallback
Where containment is required for complex data, use a "Ghost Border": `outline-variant` at 15% opacity. For a "Technical Border" look, apply this only to the corners of the container (L-shaped accents) rather than a full box.

## 5. Components

### Buttons (Tactile Triggers)
*   **Primary**: `primary-container` background, `on-primary` text. Shape is strictly `0px` radius. Use a `clip-path` to cut the top-right corner by 8px for a "mil-spec" aesthetic.
*   **Secondary**: `outline` ghost border with `primary` text. On hover, fill with `primary` at 10% opacity.
*   **Interaction**: Every click must trigger the "High-Tech Digital Click" audio sprite.

### Input Fields (Data Entry)
Background must be `surface-container-lowest`. Focus state transitions the bottom border from `outline-variant` to `primary-container` with a cinematic fade-glitch (0.2s).

### Cards & Lists (Data Clusters)
*   **Forbid Dividers**: Use `3.5rem` (16) vertical spacing or a shift from `surface-container-low` to `surface-container-high` to separate items.
*   **HUD Accents**: Add a `secondary` (#CCFF00) 2px vertical "status bar" to the left edge of an active list item.

### The "Telemetry" Component
A custom component for this system: A small, auto-scrolling log of "System Events" (e.g., `LOAD_PROJECT_01... SUCCESS`) using `label-sm` typography, placed in the bottom-left corner of the viewport.

## 6. Do's and Don'ts

### Do:
*   **Embrace the Corner**: Use sharp 0px corners everywhere. Roundness breaks the technical HUD immersion.
*   **Use Monospace-like spacing**: Align text elements to the 24px grid to maintain a "programmed" feel.
*   **Animate with Intent**: Use "Glitch" transitions (brief RGB split) during page loads or modal opens.

### Don't:
*   **Don't Use Pure White**: Use `secondary` (#FFFFFF) only for high-contrast text; for UI elements, stick to the `primary` or `surface-variant` tones to avoid "eye sear."
*   **Don't Use Standard Shadows**: Never use a `(0,0,0, 0.5)` drop shadow. It feels like a 2010s website, not a futuristic engine.
*   **Don't Center Everything**: HUDs are edge-heavy. Push navigation and status indicators to the periphery of the screen.