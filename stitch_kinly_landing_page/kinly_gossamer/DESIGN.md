# Design System Document: The Intimate Canvas

## 1. Overview & Creative North Star
**Creative North Star: "The Digital Sanctuary"**

This design system moves away from the frantic, high-stimulus patterns of traditional social media. Instead of an infinite "feed," we curate an "experience." The goal is to create a digital space that feels like a quiet room at dusk—warm, safe, and deeply personal. 

We break the "template" look by rejecting the rigid, boxy constraints of the web. By utilizing organic, asymmetrical shapes, generous breathing room (white space), and a focus on editorial-style typography, we transform the UI into a living journal. Every interaction is designed to be intentional and reflective, ensuring the user feels a sense of calm and emotional safety.

---

## 2. Colors & Atmospheric Tones
The palette is rooted in soft, muted tones that mimic natural light and shadow.

### The "No-Line" Rule
**Absolute Prohibition:** 1px solid borders for sectioning or containment are strictly forbidden. 
Boundaries must be defined through:
*   **Background Shifts:** Transitioning from `surface` to `surface-container-low`.
*   **Tonal Transitions:** Using subtle gradients between `primary` and `primary-container`.
*   **Negative Space:** Using the Spacing Scale to define "islands" of content.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked, fine papers. 
*   **Base:** `surface` (#f9f9fb)
*   **Layer 1 (Subtle grouping):** `surface-container-low` (#f2f4f6)
*   **Layer 2 (Interactive elements/Cards):** `surface-container-lowest` (#ffffff)
*   **Accent Focus:** `tertiary-container` (#ede4fd) for deeply personal or "highlighted" reflections.

### The "Glass & Gradient" Rule
To achieve a "soulful" polish, use Glassmorphism for floating navigation and modal overlays.
*   **Backdrop Blur:** Minimum 12px blur.
*   **Opacity:** 70-80% opacity on `surface-container-lowest`.
*   **Signature Gradient:** For primary actions, use a linear gradient: `primary` (#5a5b87) to `primary-fixed-dim` (#bdbcef) at a 135° angle.

---

## 3. Typography: The Editorial Journal
We use a high-contrast pairing to evoke the feeling of a bespoke literary magazine.

*   **The Voice (Display & Headlines):** *Newsreader*. This serif typeface is our emotional anchor. It feels human, authoritative yet gentle, and evokes the intimacy of a printed book. Use `display-lg` for moments of deep reflection and `headline-md` for entry titles.
*   **The Support (Body & Labels):** *Plus Jakarta Sans*. A modern, clean sans-serif that provides clarity without being cold. 
*   **Hierarchy Tip:** Use `title-lg` in *Plus Jakarta Sans* for navigation, but always revert to *Newsreader* for user-generated content to center the user's voice as the "author" of the experience.

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows are often too harsh for an emotionally safe space. We utilize "Ambient Softness."

*   **The Layering Principle:** Instead of shadows, place a `surface-container-lowest` (#ffffff) card on a `surface-container` (#eceef1) background. The slight shift in luminosity creates a natural lift.
*   **Ambient Shadows:** If a floating effect is required (e.g., a "Create" button), use:
    *   **Blur:** `32px`
    *   **Spread:** `0`
    *   **Color:** `on-surface` (#2e3336) at **4% opacity**. It should be felt, not seen.
*   **The "Ghost Border" Fallback:** If accessibility requires a stroke, use `outline-variant` (#aeb2b6) at **15% opacity**. Never use a 100% opaque border.

---

## 5. Components: Soft & Organic

### Buttons
*   **Primary:** Uses the **Signature Gradient**. Shape is `full` (pill) or `xl` (3rem) roundedness. No shadows.
*   **Secondary:** `surface-container-highest` (#dfe3e7) background with `on-surface` text.
*   **Interaction:** On hover, the button should subtly scale (1.02x) rather than change color abruptly.

### Cards & Reflections
*   **Rule:** Forbid divider lines. Use `spacing-6` (2rem) of vertical space to separate thoughts. 
*   **Shape:** Use Asymmetrical Roundedness. For example, a card might have `top-left: xl`, `top-right: md`, `bottom-right: xl`, `bottom-left: sm`. This mimics the organic shape of river stones.

### Input Fields
*   **Style:** Minimalist. No containing box. Only a subtle `surface-variant` (#dfe3e7) bottom bar or a slightly tinted `surface-container-low` background with `lg` roundedness. 
*   **Focus State:** The bottom bar transitions to `primary` (#5a5b87) with a soft glow (using the Ambient Shadow rule).

### The "Pulse" (Unique Component)
*   A soft, glowing orb using a gradient of `secondary-fixed` to `tertiary-fixed`. Used as a loading state or a "breathing" indicator during reflective prompts to ground the user.

---

## 6. Do’s and Don’ts

### Do:
*   **Embrace Asymmetry:** Align text to the left but allow images or secondary cards to sit slightly "off-grid" to create a bespoke, human feel.
*   **Use Micro-copy:** Instead of "Submit," use "Release." Instead of "Delete," use "Let go."
*   **Prioritize White Space:** If a screen feels "busy," increase the padding using the `spacing-10` or `spacing-12` tokens.

### Don’t:
*   **No Red for Errors:** Use `error-container` (#f97386) for errors. It is a softer, "blush" tone that informs the user without alarming them.
*   **No Sharp Corners:** Every element must have at least a `sm` (0.5rem) radius; however, `lg` (2rem) and `xl` (3rem) are the preferred standards for this system.
*   **No Rapid Animations:** All transitions (fade, slide, scale) must have a duration of at least 400ms with a `cubic-bezier(0.4, 0, 0.2, 1)` easing to ensure the movement feels "heavy" and calm.

---

## 7. Spacing Logic
Avoid "tight" layouts.
*   **Container Padding:** Minimum `spacing-6` (2rem) for mobile; `spacing-12` (4rem) for desktop.
*   **Gutter:** Use `spacing-4` (1.4rem) to ensure elements never feel crowded.