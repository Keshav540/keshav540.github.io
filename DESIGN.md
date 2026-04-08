```markdown
# Design System Document: The Neon Executive

## 1. Overview & Creative North Star
**Creative North Star: "The Synthetic Architect"**
This design system moves away from the chaotic, cluttered "gamer" cyberpunk aesthetic toward a high-end, editorial "Cyberpunk Professional" identity. It treats data not as noise, but as a digital landscape to be curated. By blending the brutalist sharp edges of 80s retro-futurism with the sophisticated depth of modern UI, we create an environment that feels like a high-stakes command center for a senior data analyst.

To break the "template" look, this system utilizes **Intentional Asymmetry**. Layouts should avoid perfect 50/50 splits; instead, use overlapping containers where a `surface-container-high` element might partially obscure a background graphic, creating a sense of physical depth and "active" processing.

---

## 2. Colors: The Neon & The Void
The palette is rooted in deep obsidian blacks (`background: #0e0e12`) to allow the neon accents to serve as functional wayfinding tools rather than just decoration.

*   **Primary & Secondary (The Accents):** Use `primary: #cf96ff` (Purple) and `secondary: #ff51fa` (Magenta) for high-impact actions. These are your "data highlights."
*   **The "No-Line" Rule:** Sectioning must never be done with 1px solid borders. Boundaries are defined by shifting from `surface` to `surface-container-low` (#131318). Use color blocks to define space, not outlines.
*   **Surface Hierarchy & Nesting:** Treat the UI as stacked sheets of obsidian glass. 
    *   *Base:* `surface` (#0e0e12)
    *   *Mid-Level:* `surface-container` (#19191e)
    *   *Top-Level:* `surface-container-highest` (#25252b)
*   **The "Glass & Gradient" Rule:** To achieve a premium "Retro-Futuristic" glow, use `backdrop-blur` (12px–20px) on `surface-container` elements with 80% opacity. Apply a subtle linear gradient from `primary` (#cf96ff) to `primary_dim` (#a533ff) on primary CTAs to simulate a powered-on light source.
*   **Signature Textures:** Incorporate a subtle "digital grain" or 2% noise overlay on `surface-container-lowest` to prevent the black from looking like a flat monitor-off state.

---

## 3. Typography: Bold Monospaced Professionalism
The type system balances the technical nature of data analysis with the authority of an executive.

*   **Display & Headlines (Space Grotesk):** This typeface provides the "Cyberpunk" edge. It is bold, wide, and modern. Use `display-lg` (3.5rem) for hero statements. Tighten letter-spacing by -2% for a more aggressive, editorial look.
*   **Body & Titles (Manrope):** A highly legible sans-serif that ensures the "Professional" side of the prompt is maintained. Use `body-lg` (1rem) for insights and descriptions. 
*   **Hierarchy Note:** Use `label-md` (Space Grotesk) in uppercase with 10% letter-spacing for metadata (e.g., "DATE_STAMP" or "DATA_SOURCE"). This reinforces the retro-technical aesthetic.

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows have no place here. Depth is achieved through light and opacity.

*   **The Layering Principle:** Elevate a card by placing a `surface-container-highest` (#25252b) block over a `surface` (#0e0e12) background. The sharp `0px` corners create a monolithic, architectural feel.
*   **Ambient Glows (The Shadow Alternative):** Instead of black drop shadows, use "Neon Underglows." When an element is active, apply a blurred outer glow using `primary` at 15% opacity. The blur should be large (30px+) and the spread small.
*   **The "Ghost Border" Fallback:** For secondary containers that need definition, use a `1px` border of `outline_variant` (#48474c) at **20% opacity**. It should be barely visible—a "ghost" of a line.
*   **Sharp Edges:** All `borderRadius` tokens are set to `0px`. This is non-negotiable. Soft corners dilute the futuristic professional intent.

---

## 5. Components: The Command Center
*   **Buttons:**
    *   *Primary:* Solid `primary` (#cf96ff) with `on_primary` (#480079) text. Sharp edges. No hover shadow—instead, increase the `brightness` on hover.
    *   *Secondary:* `Ghost Border` with `secondary` (#ff51fa) text. On hover, fill with `secondary_container` (#a900a9) at 20% opacity.
*   **Input Fields:** Use `surface-container-high` as the fill. The bottom border should be a `1px` line of `outline`. When focused, this line transforms into a `2px` `tertiary` (#8ff5ff) "data-stream" line.
*   **Cards:** Forbid divider lines. Use vertical white space (32px or 48px) and background shifts (`surface-container-low` to `surface-container-high`) to separate project modules.
*   **Data Chips:** Small, rectangular blocks using `tertiary_container` with `on_tertiary_fixed` text. These should look like terminal readouts.
*   **Project Timeline (Custom Component):** A vertical `1px` line using `outline_variant` with `primary` glow-nodes at each "data point."

---

## 6. Do's and Don'ts

### Do:
*   **DO** use extreme typographic scale. Make your headlines huge and your labels tiny to create an editorial feel.
*   **DO** use `tertiary` (#8ff5ff) for technical callouts or "Live" data indicators—it provides a cooling contrast to the purple/magenta heat.
*   **DO** lean into the "Professional" aspect by keeping layout grids rigid and aligned, even if elements are layered.

### Don't:
*   **DON'T** use rounded corners (`border-radius`). Ever. It breaks the "Retro-Futurist" architectural logic.
*   **DON'T** use standard grey shadows. If something needs to "pop," use a subtle purple tint in the glow or a higher surface tier.
*   **DON'T** use "gaming" tropes like heavy scanlines or glitch animations. Keep transitions smooth, fast, and high-precision (e.g., 200ms Cubic Bezier).
*   **DON'T** clutter the screen. Data analysts value signal-to-noise ratios. Use whitespace as a luxury material.

---

## 7. Interaction Pattern: "The High-Frequency Response"
Interactions should feel like interacting with a high-end mainframe. 
- **Hover:** Elements shouldn't just change color; they should "activate." A subtle increase in the backdrop-blur or a slight shift in the `primary` glow intensity is sufficient.
- **Loading:** Use a horizontal "progress stream" using the `secondary` color moving across the top of the viewport rather than a circular spinner.```