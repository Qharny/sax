# Design System Specification: The Midnight Virtuoso

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Midnight Virtuoso."** 

This system is designed to evoke the atmosphere of a high-end jazz lounge—obsidian surfaces, the warm glow of brass under a spotlight, and the tactile precision of a finely tuned instrument. We are moving away from the "utility-first" look of standard booking apps toward a **High-End Editorial** experience. 

To achieve this, we break the traditional "app grid" using intentional asymmetry, generous negative space, and a typographic hierarchy that feels more like a luxury magazine than a database. We favor **Tonal Layering** over structural lines to create a sense of organic depth and exclusivity.

---

## 2. Colors: The Palette of Resonance
The color strategy utilizes a deep, monochromatic base to allow the primary gold to act as a "visual spotlight."

### Primary & Accents
- **Primary (`#ecc246`):** Used for critical calls to action and active states. It represents the "Gold" of the instrument.
- **Primary Container (`#c9a227`):** Used for subtle emphasis or large-format backgrounds where a softer gold is required.
- **Secondary (`#c6c6c6`):** Our "Silver" accent, providing a cool counterpoint to the warm gold.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to section off content. Boundaries must be defined solely through background color shifts. Use `surface-container-low` for sections sitting on a `surface` background. The eye should perceive change through tone, not lines.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—like stacked sheets of frosted glass.
- **Base Layer:** `surface` (`#131313`)
- **Inset/Sunken Elements:** `surface-container-lowest` (`#0e0e0e`)
- **Raised Cards:** `surface-container-high` (`#2a2a2a`)
- **Floating Elements:** `surface-container-highest` (`#353534`)

### The "Glass & Gradient" Rule
To elevate the "out-of-the-box" feel, use **Glassmorphism** for navigation bars and floating overlays. Use semi-transparent versions of `surface-variant` with a `backdrop-filter: blur(20px)`. For Hero sections, apply a subtle linear gradient from `primary` to `primary-container` at a 135-degree angle to provide a metallic "soul" to the surface.

---

## 3. Typography: Rhythmic Precision
We pair the structural, bold nature of **Epilogue** with the modern, fluid legibility of **Manrope**.

- **Display & Headlines (Epilogue):** These are the "Lead Soloists." Use `display-lg` (3.5rem) for hero statements and `headline-lg` (2rem) for section starts. The weight should be Bold to create high contrast against the dark backgrounds.
- **Titles & Body (Manrope):** These are the "Rhythm Section." Use `title-lg` (1.375rem) for card headers and `body-lg` (1rem) for descriptions. 
- **Character:** Epilogue’s geometric quirks feel musical and architectural, while Manrope’s clean finish ensures that even complex booking details remain effortless to read.

---

## 4. Elevation & Depth: Tonal Layering
In this system, depth is felt, not seen. We reject heavy drop shadows in favor of light-based elevation.

- **The Layering Principle:** Instead of a shadow, place a `surface-container-low` card on a `surface-container-lowest` background. This creates a "soft lift."
- **Ambient Shadows:** When a floating effect is mandatory (e.g., a primary Action Button), use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(0,0,0, 0.4)`. The shadow should never be a neutral grey; it should feel like a deep tint of the background color.
- **The "Ghost Border" Fallback:** If a container requires more definition for accessibility, use the `outline-variant` token at **15% opacity**. This creates a whisper of an edge that disappears into the luxury aesthetic.
- **Glassmorphism:** Use `surface-bright` at 60% opacity with a heavy blur for elements that need to sit "above" the music, such as date pickers or profile modals.

---

## 5. Components

### Buttons
- **Primary:** Background `primary`, text `on-primary`. Roundedness: `xl` (3rem). These should feel like "pills."
- **Secondary:** Background `secondary-container`, text `on-secondary-container`. Roundedness: `xl`.
- **Tertiary:** No background. Use `primary` text with a `label-md` weight.

### Cards & Lists
- **Rule:** **Strictly forbid divider lines.** 
- Separate list items using 1.5rem (md) of vertical white space or by alternating background tones between `surface-container-low` and `surface-container-high`.
- **Roundedness:** All cards must use `lg` (2rem) or `xl` (3rem) corner radii to maintain the "Soft Minimalism" feel.

### Chips (Genre/Availability)
- Use `surface-container-highest` for unselected states and `primary` for selected states. 
- Roundedness: `full` (9999px).

### Input Fields
- Background: `surface-container-lowest`. 
- Border: None, except for a 2px `primary` bottom-border only when **focused**.
- Placeholder text: `on-surface-variant` at 50% opacity.

### Featured Component: The "Virtuoso Profile Card"
A large-format card using a background image with a `surface-dim` gradient overlay. Typography should overlap the edge of the image slightly to create an editorial, "layered" look.

---

## 6. Do's and Don'ts

### Do
- **Do** use asymmetrical margins (e.g., 24px left, 32px right) for headline placements to create a custom, high-end feel.
- **Do** use "Breathing Room." If you think there is enough padding, add 8px more.
- **Do** use the `primary` gold for iconography, but keep the icons thin (2pt stroke) to match the luxury aesthetic.

### Don't
- **Don't** use pure `#000000` for backgrounds. It kills the depth. Use the `surface` tokens.
- **Don't** use standard Material Design ripples. Use a soft "fade-to-gold" transition for touch states.
- **Don't** crowd the interface. If a screen feels busy, move secondary information into a "Details" modal.
- **Don't** use high-contrast white text (`#FFFFFF`). Use `on-surface` (`#e5e2e1`) to reduce eye strain and maintain the "Midnight" mood.