# Design System Specification: The Ethereal Professional

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Digital Architect."** It represents a shift away from the "flat web" toward a space that feels engineered, deep, and precisely illuminated. We are not just building a dark-themed app; we are constructing a high-end digital environment where light doesn't just exist—it *emits* from the core interactions.

To break the "template" look, we prioritize **Intentional Asymmetry** and **Tonal Depth**. Instead of rigid, centered grids, we use white space (or "dark space") as a functional element to guide the eye. Overlapping elements and ultra-large display type create a sense of editorial authority, making the application feel like a custom-designed experience rather than a generic dashboard.

---

## 2. Colors & Surface Architecture

The palette is anchored in deep neutrals (`#0e0e0e`) and punctuated by high-frequency accents.

### The "No-Line" Rule
**Borders are a design failure in this system.** To section off content, designers must never use 1px solid lines. Boundaries are defined through:
- **Tonal Shifts:** Placing a `surface-container-high` (`#20201f`) element on top of a `surface` (`#0e0e0e`) background.
- **Negative Space:** Using the spacing scale to create distinct islands of content.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of materials. 
1.  **Base Layer:** `surface-dim` (`#0e0e0e`) - The infinite canvas.
2.  **Section Layer:** `surface-container-low` (`#131313`) - Large structural areas.
3.  **Interaction Layer:** `surface-container-high` (`#20201f`) - Cards and interactive modules.
4.  **Elevation Layer:** `surface-bright` (`#2c2c2c`) - Popovers and floating menus.

### The "Glass & Gradient" Rule
To achieve "professional polish," CTAs and primary actions should utilize a subtle linear gradient from `primary` (`#a3a6ff`) to `primary_dim` (`#6063ee`) at a 135-degree angle. Floating panels must use **Glassmorphism**: apply `surface_container` with 80% opacity and a `20px` backdrop-blur to allow the deep background tones to bleed through.

---

## 3. Typography

We utilize a dual-typeface system to balance professional rigor with creative flair.

*   **Display & Headlines (Manrope):** This is our "Editorial" voice. Manrope’s geometric yet warm curves provide the "Creative" aesthetic. Use `display-lg` (3.5rem) with tight letter-spacing (-0.02em) for high-impact hero moments.
*   **Body & Labels (Inter):** Our "Functional" voice. Inter is used for maximum readability in the dark theme. 

**The Typographic Hierarchy:**
- **Display (L/M/S):** For "wow" moments and section headers.
- **Headline (L/M/S):** For page titles and primary content headers.
- **Title (L/M/S):** For card titles and secondary navigation.
- **Body (L/M/S):** For all long-form reading. Use `on_surface_variant` (`#adaaaa`) for body-md to reduce eye strain against the black background.

---

## 4. Elevation & Depth

### The Layering Principle
Depth is achieved by "stacking" surface tiers. To make a card feel "raised," do not use a shadow first; instead, move from `surface` to `surface-container-highest` (`#262626`).

### Ambient Shadows
If a floating element (like a Modal) requires a shadow, it must be an **Ambient Shadow**:
- **Color:** `#000000` at 40% opacity.
- **Blur:** 40px to 60px.
- **Spread:** -10px.
- This creates a soft "lift" rather than a harsh edge.

### The "Ghost Border" Fallback
Where accessibility requirements demand a container boundary, use a **Ghost Border**: `outline_variant` (`#484847`) at 15% opacity. It should be felt, not seen.

---

## 5. Components

### Buttons
*   **Primary:** Gradient of `primary` to `primary_dim`. Roundedness: `md` (0.375rem). Use `on_primary` (`#0f00a4`) for text to ensure high-contrast legibility.
*   **Secondary:** Ghost style. `outline` border at 20% opacity with `primary` text.
*   **Tertiary:** No background. `primary` text with a subtle underline on hover.

### Cards & Lists
*   **Forbidden:** Divider lines between list items.
*   **Requirement:** Use 16px to 24px of vertical padding to separate items. For lists, use a subtle hover state transition to `surface-container-highest`.

### Input Fields
*   **State:** Default state uses `surface-container-highest` as the background.
*   **Focus State:** The background remains the same, but a 1px "Ghost Border" of `primary` at 50% opacity appears, accompanied by a soft `primary` outer glow (4px blur).

### Chips
*   **Interactive:** Use `secondary_container` (`#4d329b`) with `on_secondary_container` text. These should feel like small "jewels" in the layout.

---

## 6. Do’s and Don'ts

### Do:
*   **Embrace "Void" Space:** Let the `background` (`#0e0e0e`) breathe. High-end design is defined by what you leave out.
*   **Use Tonal Transitions:** Shift background colors slightly when a user scrolls to signal a change in context.
*   **Optical Alignment:** When using Manrope Display type, visually align the "edge" of the letterforms rather than the bounding box.

### Don't:
*   **No Pure White Text:** Avoid using `#ffffff` for long body copy; use `on_surface_variant` (`#adaaaa`) to prevent "halation" (the glowing effect of white text on black backgrounds).
*   **No Default Shadows:** Never use the standard `0px 2px 4px` shadows. They look "cheap" in a high-end dark UI.
*   **No Hard Dividers:** Never use a solid line to separate the header from the body. Use a background color shift or a blur effect.

---

## 7. Signature Elements: The "Aura"
To reinforce the creative aesthetic, use **Radial Aura Blurs**. Place large, low-opacity (5-10%) blobs of `secondary` (`#a98ffd`) or `tertiary` (`#ff9dd1`) deep in the background layers. These should not be interactive; they serve as "atmospheric lighting" to break up the charcoal surfaces and add a sense of premium art direction.