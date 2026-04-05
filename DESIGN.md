# Design System Document: The Kinetic Stadium

## 1. Overview & Creative North Star
**Creative North Star: "The Kinetic Stadium"**

This design system moves away from the generic "SaaS dashboard" look to embrace the high-stakes, high-energy atmosphere of professional cricket under stadium floodlights. We are building a "Digital HUD" (Heads-Up Display) for the modern manager. 

To achieve a high-end editorial feel, the layout must reject the rigid, centered grid. Instead, we utilize **Intentional Asymmetry**. Large-scale typography should bleed off-canvas or overlap image containers, creating a sense of forward motion. This isn't just a landing page; it is a premium sports broadcast experience translated into a digital interface.

---

## 2. Colors & Surface Philosophy
The palette is rooted in a deep, atmospheric dark mode, punctuated by the electric energy of the pitch.

### The Color Palette
- **Primary (`#97a9ff`):** Used for technical UI elements and data visualization. Represents the "managerial" aspect.
- **Secondary (`#c3f400`):** Our high-energy "Pitch Green." This is reserved for CTAs and critical success states.
- **Tertiary (`#a1faff`):** Used for accents, secondary highlights, and "glass" reflections.

### The "No-Line" Rule
**Strict Mandate:** Traditional 1px solid borders are prohibited for sectioning or containment. 
Boundary definition must be achieved through:
1.  **Background Shifts:** Transition from `surface` (`#0c0e12`) to `surface-container-low` (`#111318`) to define section breaks.
2.  **Tonal Depth:** Placing a `surface-container-high` card on a `surface-container` background.

### The "Glass & Gradient" Rule
To elevate the "Cricket Manager" aesthetic, use Glassmorphism for floating overlays (e.g., player stat cards). 
- **Recipe:** Use `surface-container` at 60% opacity with a 20px backdrop-blur. 
- **Gradients:** Apply a subtle linear gradient from `primary-dim` (`#3e65ff`) to `primary` (`#97a9ff`) on primary action buttons to give them a tactile, "lit" quality.

---

## 3. Typography
The typography strategy creates a tension between technical precision and bold sports editorial.

- **Display & Headlines (Space Grotesk):** This is our "Stadium Voice." Use `display-lg` for hero statements. It should feel massive, commanding, and slightly technical. Decrease letter-spacing by -2% for headlines to create a "locked-in" professional feel.
- **Body & Labels (Manrope):** This is our "Strategy Voice." It provides a clean, modern contrast to the aggressive headlines.
- **Hierarchy:** Use `label-md` in all-caps with increased letter-spacing (+10%) for category tags (e.g., "LIVE MATCH," "PLAYER STATS") to mimic the look of a broadcast ticker.

---

## 4. Elevation & Depth: Tonal Layering
We do not use shadows to simulate height; we use light and material density.

### The Layering Principle
Construct the UI as a series of nested physical layers:
1.  **Floor:** `background` (`#0c0e12`).
2.  **Sections:** `surface-container-low` (`#111318`) for large content blocks.
3.  **Floating Elements:** `surface-container-highest` (`#23262c`) for interactive cards.

### Ambient Shadows
If a "floating" effect is required for a modal or a primary CTA, use a diffused shadow:
- **Shadow Color:** A 10% opacity version of `primary` (`#97a9ff`) to simulate light reflecting off the digital grass.
- **Blur:** 40px - 60px for a soft, atmospheric glow.

### The Ghost Border
For accessibility on interactive fields, use a **Ghost Border**: a 1px stroke using `outline-variant` (`#46484d`) at 20% opacity. It should feel felt, not seen.

---

## 5. Components

### Buttons
- **Primary CTA:** Uses `secondary` (`#c3f400`) with `on-secondary` (`#455900`) text. Shape: `full` roundedness. This is the "high-conversion" trigger.
- **Secondary CTA:** A `ghost` style with `outline` token and `primary` text. Use for "Learn More" or secondary gallery navigation.

### Feature Cards
- **Construction:** Use `surface-container-high` (`#1d2025`) with `xl` (0.75rem) corner radius. 
- **Rule:** No dividers. Separate the card title from the body text using a 1.5rem vertical gap (Spacing Scale).
- **Interactive State:** On hover, the card should transition to `surface-container-highest` and the `primary` accent should glow subtly at the top edge.

### The "Stat-Chip"
A custom component for the app's gallery section. 
- **Style:** `surface-variant` background, `sm` (0.125rem) roundedness for a technical, data-heavy look.
- **Typography:** Use `label-sm` for the metric and `title-sm` for the value.

### Input Fields
- **Background:** `surface-container-lowest` (`#000000`).
- **Indicator:** Use a 2px bottom bar of `primary` (`#97a9ff`) when focused, rather than a full box stroke.

---

## 6. Do's and Don'ts

### Do
- **Do** overlap images and text. Let a player's shoulder mask behind a `display-lg` headline.
- **Do** use `secondary_dim` for subtle hover states on green elements to maintain color depth.
- **Do** use the Spacing Scale aggressively. High-end design requires "white space" (or in this case, "dark space") to breathe.

### Don't
- **Don't** use pure white (`#FFFFFF`) for body text. Always use `on-surface` (`#f6f6fc`) or `on-surface-variant` (`#aaabb0`) to reduce eye strain and maintain the premium dark aesthetic.
- **Don't** use standard 1px grey borders. It breaks the immersive "stadium" feel and makes the UI look like a template.
- **Don't** use generic icons. Use thick-stroke, geometric icons that match the weight of Space Grotesk.