# Design System Specification: Clinical Precision & Tonal Depth

## 1. Overview & Creative North Star: "The Digital Surgeon"
This design system is built upon the North Star of **"The Digital Surgeon."** It rejects the cluttered, chaotic nature of traditional medical software in favor of extreme clarity, rhythmic spacing, and authoritative calm. 

To achieve a "High-End Editorial" feel, we move away from generic templates. We utilize **intentional asymmetry**—such as oversized headlines balanced by vast amounts of negative space—and **tonal layering** to create a sense of focused expertise. The experience should feel less like an app and more like a high-precision medical instrument: deliberate, expensive, and unerringly accurate.

---

## 2. Colors & Surface Architecture
The color palette is rooted in "Clinical Titanium" to establish a sterile, high-tech environment. 

### The Palette
- **Primary (Electric Blue):** `#0059bb` — Used for high-velocity actions and critical focus points.
- **Secondary (Vibrant Teal):** `#006b5c` — Used for "Success" states, health indicators, and secondary affirmations.
- **Background (Titanium White):** `#f7f9fc` — The sterile canvas for all interactions.
- **On-Surface (Deep Slate):** `#191c1e` — High-contrast typography for maximum legibility in the Indian mobile market.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to section content. Traditional "boxes" make an interface feel dated and rigid. Instead, boundaries must be defined through:
1.  **Background Color Shifts:** Use `surface-container-low` sections sitting on a `surface` background.
2.  **Tonal Transitions:** A subtle shift from `surface` to `surface-container-highest` defines the end of a section.

### The "Glass & Gradient" Rule
To inject "visual soul" into a clinical environment:
- **Signature Textures:** For Hero sections or primary CTAs, use a subtle linear gradient transitioning from `primary` (#0059bb) to `primary-container` (#0070ea) at a 135-degree angle.
- **Glassmorphism:** Floating action headers or modal overlays must use `surface-container-lowest` with a 70% opacity and a `24px` backdrop-blur. This ensures the clinical background "bleeds through," making the UI feel like a single, integrated piece of hardware.

---

## 3. Typography: The Editorial Hierarchy
The system uses a dual-font approach to balance authority with accessibility.

*   **Display & Headlines (Manrope):** A modern geometric sans-serif with a high x-height. It feels authoritative and architectural. Use `display-lg` (3.5rem) for hero data points and `headline-md` (1.75rem) for section titles.
*   **Body & Labels (Inter):** Chosen for its exceptional legibility on low-resolution mobile screens common in the Indian market. Use `body-md` (0.875rem) for primary medical data and `label-sm` (0.6875rem) for micro-copy and metadata.

**Editorial Tip:** Use "Tonal Contrast" in typography. Pair a `headline-lg` in `on-surface` with a `body-sm` in `on-surface-variant` (lower opacity) to create a clear information hierarchy without needing lines.

---

## 4. Elevation & Depth: Tonal Layering
We do not use shadows to create "pop"; we use layers to create "logic."

*   **The Layering Principle:** 
    *   **Base:** `surface` (#f7f9fc)
    *   **Sections:** `surface-container-low` (#f2f4f7)
    *   **Cards/Interactive Elements:** `surface-container-lowest` (#ffffff)
    *   **Active Overlays:** `surface-container-highest` (#e0e3e6)
*   **Ambient Shadows:** If a floating element (like a FAB) is required, use a shadow color tinted with the primary navy: `rgba(26, 43, 60, 0.06)` with a `32px` blur and `8px` Y-offset.
*   **The "Ghost Border" Fallback:** If a container must be defined against a white background, use the `outline-variant` token at **15% opacity**. Never use a 100% opaque border.

---

## 5. Components

### Buttons: High-Velocity Action
- **Primary:** `primary` background with `on-primary` text. Use `DEFAULT` (0.25rem) roundedness for a sharp, clinical look. 
- **Secondary:** Transparent background with a `secondary` ghost border (20% opacity).
- **Tertiary:** Text-only in `primary` color, strictly aligned to the grid's right edge for editorial balance.

### Input Fields: Clinical Precision
- **Style:** Minimalist. No background fill. Only a bottom "Ghost Border" using `outline-variant`. 
- **States:** On focus, the bottom border transitions to `primary` (2px thickness), and the label shrinks using `label-md` tokens.

### Cards & Lists: The "Invisible Grid"
- **Rules:** Forbid the use of divider lines.
- **Implementation:** Separate list items using `16px` of vertical white space. If items need distinct grouping, alternate background colors between `surface` and `surface-container-low`.

### Medical Badges (Context Specific)
- **Status Badges:** Use `secondary-container` for "Stable" and `error-container` for "Alert." Badges should use `full` roundedness (capsule) and `label-sm` bold typography to denote medical legitimacy.

### Data Visualization
- **The Precision Chart:** Use the `secondary` (Teal) for positive trends and `primary` (Blue) for neutral benchmarks. Lines should be 2pt thick with "sharp" joints to maintain the high-tech aesthetic.

---

## 6. Do's and Don'ts

### Do:
- **Do** use extreme white space. If you think there is enough space, add 8px more.
- **Do** use "surface nesting" to group related medical data.
- **Do** ensure all touch targets for the mobile-first Indian market are at least 48x48dp, even if the visual element is smaller.

### Don't:
- **Don't** use pure black (#000000). Always use `on-surface` (Deep Slate).
- **Don't** use standard "drop shadows" that look like 2010-era software. Stick to tonal shifts.
- **Don't** use soft, bubbly rounded corners. Stick to the specified `0.25rem` (sm/md) to maintain a "scientific instrument" feel.
- **Don't** use icons without labels. In a medical context, precision is more important than visual minimalism.