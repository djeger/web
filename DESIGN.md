# Design System Strategy: The Tactile Neon Tabletop

## 1. Overview & Creative North Star
**Creative North Star: "The Digital Game Night"**

This design system moves away from the sterile, flat "SaaS" look and embraces the tactile, high-energy atmosphere of a late-night board game session. We are not just building an interface; we are arranging game components on a premium, dark felt table. 

To break the "template" look, we employ **intentional asymmetry** and **component-based elevation**. UI elements should never feel like static boxes; they should feel like cards that have been dealt, tokens that have been placed, and dice that have been rolled. By utilizing high-contrast typography scales and overlapping elements, we create a sense of depth and "controlled chaos" that mirrors the excitement of tabletop gaming.

---

## 2. Colors & Surface Philosophy
The palette is anchored by a deep, midnight foundation (`background: #0c0e17`), allowing our neon "game pieces" to pop with radioactive intensity.

*   **Primary (`#81ecff`):** Our "Electric Blue" mana. Used for interactive "Power-Ups" (Primary CTAs) and active states.
*   **Secondary (`#e966ff`):** Our "Neon Purple" mystery. Used for secondary actions and magical accents.
*   **Tertiary (`#ffa44c`):** Our "Vibrant Orange" energy. Reserved for critical alerts, notifications, or "Legendary" status items.

### The "No-Line" Rule
**Borders are forbidden for sectioning.** To define space, use background color shifts. A `surface-container-low` section sitting on a `surface` background creates a clean, sophisticated break. If you feel the urge to draw a line, use a `16px` (spacing 4) gap instead.

### The "Glass & Gradient" Rule
To give the UI "soul," use subtle gradients for main CTAs, transitioning from `primary` to `primary-container`. For floating elements, use **Glassmorphism**: apply a semi-transparent `surface-variant` with a `backdrop-blur` of 12px. This makes the UI feel like it's made of high-end acrylic game tokens.

---

## 3. Typography: Editorial Playfulness
We pair the technical precision of **Space Grotesk** with the friendly, readable warmth of **Plus Jakarta Sans**.

*   **Display & Headlines (Space Grotesk):** These are your "Game Titles." Use `display-lg` (3.5rem) for hero moments. The wide apertures and geometric shapes of Space Grotesk feel modern and slightly "tech," fitting for a contemporary club.
*   **Body & Titles (Plus Jakarta Sans):** These are your "Rulebook Text." `body-md` (0.875rem) provides maximum readability against dark backgrounds.
*   **Labels (Space Grotesk):** Use `label-md` for "Stats"—player counts, times, and difficulty ratings. It adds a professional, organized feel to small data points.

---

## 4. Elevation & Depth: Tonal Layering
In this system, "Up" is "Brighter." We do not use traditional drop shadows that look like "web shadows"; we use light and color to lift objects.

*   **The Layering Principle:** 
    *   **Level 0 (The Table):** `surface` (#0c0e17)
    *   **Level 1 (The Game Board):** `surface-container-low` (#11131d)
    *   **Level 2 (The Cards):** `surface-container` (#171924)
    *   **Level 3 (The Tokens):** `surface-container-high` (#1c1f2b)
*   **Ambient Shadows:** If an element must "float" (like a modal), use an ultra-diffused shadow: `box-shadow: 0 20px 40px rgba(0, 227, 253, 0.08)`. Note the tint—we use the `primary` color for the shadow to simulate neon glow.
*   **The "Ghost Border" Fallback:** If a container needs more definition, use `outline-variant` at 15% opacity. It should feel like a faint light catch on the edge of a plastic card.

---

## 5. Components

### The "Game Card" (Standard Container)
*   **Shape:** `rounded-lg` (1rem). 
*   **Surface:** `surface-container`.
*   **Interaction:** On hover, shift to `surface-container-highest` and lift by 4px using a slight transform. **Never use dividers.** Use `spacing-4` (1rem) to separate internal content.

### Buttons (The Action Tokens)
*   **Primary:** `primary` background with `on-primary` text. Use `rounded-full` (9999px) to make it feel like a tactile token.
*   **Secondary:** `surface-container-highest` background with `secondary` text. 
*   **Tertiary:** Ghost style. No background, `primary` text, `label-md` uppercase.

### Input Fields (The Player Slots)
*   **Style:** `surface-container-lowest` (pure black) background to create an "inset" feel, like a slot in a board game tray.
*   **Active State:** 1px `primary` ghost border (20% opacity) with a subtle `primary` outer glow.

### Chips (The Resource Markers)
*   Used for game genres (e.g., "Strategy," "Deckbuilder"). 
*   `surface-bright` background with `on-surface-variant` text. When selected, swap to `secondary-container` with `on-secondary-container` text.

### Progress Bars (The Health/XP Track)
*   Track: `surface-container-highest`.
*   Indicator: Gradient from `secondary` to `primary`.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** lean into the "Card" aesthetic. Overlap elements slightly (e.g., a "New" badge overlapping the corner of a game card).
*   **Do** use `primary` and `secondary` gradients for high-value interactions.
*   **Do** use the Spacing Scale strictly. Generous breathing room (`spacing-8` or `spacing-10`) is what makes a dark theme feel "Premium" instead of "Cluttered."

### Don’t:
*   **Don’t** use pure white (`#FFFFFF`) for body text. Use `on-surface` (#f0f0fd) to reduce eye strain.
*   **Don’t** use 1px solid borders to separate list items. Use a `surface-container-low` background on every second item, or simply use whitespace.
*   **Don’t** use standard "web" reds for errors. Use our bespoke `error` (#ff6e84) which is tuned to vibrate correctly against the dark blue background.