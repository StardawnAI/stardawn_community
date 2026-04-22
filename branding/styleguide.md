# Design System Strategy: Neon Noir & Celestial Intelligence

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Celestial Nexus."** We are moving beyond the standard SaaS "dark mode" into a high-end, editorial space that feels like a portal into a high-tech future. 

The system leverages the sharp contrast between absolute void (Pure Black) and hyper-luminous accents. Unlike traditional grids that rely on borders to contain ideas, this system uses **intentional asymmetry** and **tonal depth** to guide the eye. We prioritize a "Glass-on-Void" aesthetic—where elements don't just sit on the background; they float within it, emitting their own light. This is an experience of depth, air, and luminescence.

---

## 2. Colors: The Void and The Pulse
The palette is hyper-restricted to maintain a premium, high-tech feel. We rely on luminosity rather than hue variety.

| Role | Token | Hex | Usage |
| :--- | :--- | :--- | :--- |
| **The Void** | `surface` / `background` | `#000000` | The infinite base. Never use dark grey for the primary background. |
| **The Pulse** | `primary` | `#4cd7f6` | Glowing accents, CTAs, and critical interactive paths. |
| **Celestial White** | `on-background` | `#FFFFFF` | Primary typography with a subtle 2px glow effect. |
| **Glass Base** | `surface-container` | `#131313` | Semi-transparent layers for glassmorphism. |

### The "No-Line" Rule
Prohibit the use of 1px solid borders for sectioning. Structural separation must be achieved through:
1. **Background Shifting:** Moving from `#000000` to a `surface-container-low` (`#1b1b1b`) to define a new content zone.
2. **Negative Space:** Utilizing the `20` (5rem) and `24` (6rem) spacing tokens to create breathing room that acts as a natural separator.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers of obsidian and frosted glass. 
*   **Base:** `surface` (#000000)
*   **Level 1 (Sections):** `surface-container-low` (#1b1b1b)
*   **Level 2 (Cards):** `surface-container` (#1f1f1f) with a `backdrop-blur` of 20px.
*   **Level 3 (Modals/Popovers):** `surface-container-highest` (#353535) with 40% opacity.

### The "Glass & Gradient" Rule
Main CTAs and high-priority hero elements should not be flat. Use a linear gradient from `primary` (#4cd7f6) to `primary-container` (#005b6b) at a 135-degree angle to provide "visual soul."

---

## 3. Typography: Mathematical Precision
We use a dual-typeface system to balance high-tech geometry with editorial readability.

*   **Display & Headlines (Space Grotesk):** This is our "Engineered" voice. Its geometric apertures feel futuristic and authoritative.
    *   *Styling Note:* Use `display-lg` (3.5rem) with `-0.02em` letter spacing to create a tight, cinematic impact.
*   **Body & Titles (Plus Jakarta Sans):** Our "Human" voice. It provides high legibility against high-contrast backgrounds.
    *   *Styling Note:* Body text should never be pure white. Use `on-surface-variant` (#bcc9cd) to prevent eye strain and maintain a premium, dimmed aesthetic.

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows are prohibited. Depth is achieved through light emission and transparency.

*   **The Layering Principle:** Place a `surface-container-lowest` card on a `surface-container-low` section. The subtle shift in hex value creates a "soft lift" without structural bulk.
*   **Ambient Glows:** Instead of a drop shadow, floating elements use a "Cyan Aura." Apply a drop-shadow effect: `0px 0px 20px rgba(76, 215, 246, 0.15)`. This mimics light reflecting off a surface.
*   **The "Ghost Border" Fallback:** If a container needs a boundary, use the `outline-variant` (#3d494c) at 20% opacity. It should feel like a faint reflection on the edge of a glass pane.
*   **Glassmorphism:** Apply `backdrop-filter: blur(12px)` to all container elements. This allows the "void" and any background gradients to bleed through, integrating the UI into the environment.

---

## 5. Components: Engineered Elements

### Buttons
*   **Primary:** Gradient fill (`primary` to `primary-container`), white text, `xl` (1.5rem) roundedness. Add a subtle glow on hover.
*   **Tertiary (Ghost):** No background. `primary` text with a 1px `Ghost Border`.

### Cards
*   **Rule:** Forbid divider lines.
*   **Structure:** Use `surface-container` with a 15% opacity. The border should be a `primary` glow, but only at 0.5px thickness and 40% opacity.
*   **Layout:** Use asymmetrical padding (e.g., `padding-left: 2.5rem`, `padding-right: 1.5rem`) to create a bespoke, non-template feel.

### Input Fields
*   **State:** Unfocused inputs are `surface-container-lowest` with a "Ghost Border."
*   **Focus:** The border transitions to 100% opacity `primary` with a 4px outer glow.

### Interactive "Orbs" (Contextual Component)
For an AI-driven platform, use floating, semi-transparent orbs in the background that respond to cursor movement. These use `primary` and `tertiary` tokens with a 100px blur filter to create a "nebula" effect.

---

## 6. Do's and Don'ts

### Do
*   **Do** use extreme vertical spacing. Give elements room to "breathe" in the void.
*   **Do** use `spaceGrotesk` for all numerical data and labels to emphasize the "high-tech" look.
*   **Do** apply a subtle text-shadow to `display` headings: `0 0 8px rgba(255,255,255,0.3)`.

### Don't
*   **Don't** use purple, violet, or warm tones. The palette must remain strictly "Cold Tech" (Cyan/Black/White).
*   **Don't** use 100% opaque borders. They break the illusion of light and glass.
*   **Don't** use standard "Grey" (#808080). Use the `outline` (#869397) or `on-surface-variant` (#bcc9cd) tokens which are slightly tinted toward cyan to maintain color harmony.
*   **Don't** use sharp 90-degree corners. Refer to the Roundedness Scale; even "sharp" elements should have at least the `sm` (0.25rem) radius to feel premium.