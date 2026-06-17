# Design System Document: The Curated Sanctuary

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Curated Sanctuary."** 

This system is not a utility; it is an atmosphere. We are moving away from the "template" look of traditional SaaS products and toward the feeling of a high-end, physical gallery or an organic architectural space. This is achieved through **intentional asymmetry**, where negative space is treated as a functional element rather than "empty" space. By overlapping editorial imagery with glassmorphic containers and using high-contrast typography scales, we create a digital experience that feels tactile, premium, and calm.

## 2. Color & Atmospheric Depth
Our palette is rooted in the natural world, utilizing a soft ivory base with organic, vibrant accents.

### The Color Palette
- **Background (`#fbf9f6`):** Our foundation. It is warmer than pure white, providing a soft, paper-like quality that reduces eye strain and conveys luxury.
- **Primary (`#4f6357`):** A sophisticated sage green representing sustainability and groundedness.
- **Secondary (`#6e5c33`):** A warm, sun-drenched yellow for subtle highlights.
- **Tertiary (`#7c554e`):** A muted blush pink to provide a human, organic touch.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders for sectioning or containment. Boundaries must be defined through:
1.  **Background Color Shifts:** Use `surface-container-low` sections sitting on a `surface` background to define areas.
2.  **Tonal Transitions:** Use soft, cloudy gradients (Sage to Ivory) to guide the eye from one content block to the next.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—like stacked sheets of fine, semi-translucent paper.
- **Base Layer:** `surface`
- **Low-Priority Containers:** `surface-container-low` (used for secondary content).
- **Interactive/Primary Containers:** `surface-container-lowest` (pure `#ffffff`) to create a soft "pop" against the ivory background.

### The "Glass & Gradient" Rule
To achieve the "Cloudy Vibrant" aesthetic, use the **Primary**, **Secondary**, and **Tertiary** colors as large, blurred background "blobs" (300px+ blur) behind glassmorphic surfaces. 
- **Glassmorphism:** Use `surface` or `surface-container-lowest` at 60-80% opacity with a `backdrop-blur` of 20px–40px for floating elements like the Navbar.

---

## 3. Typography
The typography system relies on the tension between a high-fashion editorial serif and a highly legible, modern sans-serif.

### Display & Headlines (Newsreader)
- **Role:** Authority and Grace.
- **Usage:** All `display` and `headline` levels must use **Newsreader**. 
- **Design Note:** Use `display-lg` (3.5rem) with generous leading to create "hero moments." Do not be afraid to let headlines overlap slightly with image containers to break the grid.

### Titles & Body (Manrope)
- **Role:** Clarity and Utility.
- **Usage:** All `title`, `body`, and `label` levels must use **Manrope**.
- **Design Note:** Use `body-lg` for product descriptions to maintain a premium, readable feel. Labels should be tracked out (+2% to +5%) for a sophisticated, technical look.

---

## 4. Elevation & Depth
In this design system, depth is a result of light and shadow, not lines and boxes.

### The Layering Principle
Depth is achieved by "stacking" the surface tiers. Place a `surface-container-lowest` card on a `surface-container-low` section. This creates a natural, soft lift that mimics high-quality stationery.

### Ambient Shadows
Shadows are rarely used, but when necessary for floating action buttons or modal windows:
- **Style:** Extra-diffused.
- **Values:** Blur 40px–60px, Opacity 4%–8%.
- **Color:** Use a tinted version of `on-surface` (dark green-grey) rather than pure black to keep the "calm" vibe.

### The "Ghost Border" Fallback
If a border is required for accessibility (e.g., in a high-density list), use the **Ghost Border**:
- **Token:** `outline-variant` at 15% opacity. 
- **Requirement:** 100% opaque borders are strictly forbidden.

---

## 5. Components

### Buttons
- **Primary:** Use `primary` background with `on-primary` text. Roundedness: `full`. No shadow; use a subtle gradient transition to `primary-container` on hover.
- **Secondary:** Use `surface-container-highest` background. Roundedness: `full`.
- **Tertiary (Ghost):** No background. Use `primary` text with a `label-md` weight.

### Navigation Bar
- **Style:** Floating Glassmorphism.
- **Color:** `surface` at 70% opacity.
- **Effect:** `backdrop-blur: 32px`.
- **Border:** A single `Ghost Border` on the bottom edge only.

### Product Cards
- **Structure:** No borders. Use `surface-container-lowest` as the card base. 
- **Roundedness:** `xl` (1.5rem).
- **Spacing:** Extreme internal padding (minimum 2rem) to allow the product photography to breathe.
- **Separation:** Use vertical white space rather than dividers.

### Input Fields
- **Background:** `surface-container-low`.
- **Roundedness:** `md`.
- **Active State:** A subtle `primary` glow (4px blur at 20% opacity) rather than a heavy stroke.

### Chips & Filters
- **Style:** "Pill" shape (`full`).
- **Inactive:** `surface-variant`.
- **Active:** `primary-fixed` with `on-primary-fixed` text.

---

## 6. Do’s and Don’ts

### Do
- **Do** use large, high-quality imagery that features natural light and organic textures.
- **Do** lean into asymmetry. For example, a 2-column layout where the left column is 60% width and the right is 40%.
- **Do** use `surface-dim` for "scrims" behind modals to maintain the warm, ivory tone.

### Don’t
- **Don't** use pure black (#000000) for text. Always use `on-surface` (#1b1c1a).
- **Don't** use standard 8px padding. Our spacing scale should feel "oversized"—prefer 24px, 32px, and 48px increments.
- **Don't** use sharp corners. Every container must have at least `md` (0.75rem) roundedness to maintain the "Soft Minimalism" aesthetic.
- **Don't** use horizontal divider lines. If content needs to be separated, use a 64px vertical gap or a subtle change in background tone.