# Design System Specification: High-End Editorial

## 1. Overview & Creative North Star: "The Digital Architect"
The Creative North Star for this design system is **The Digital Architect**. We are moving away from the "template" look of generic SaaS platforms to an editorial experience that feels curated, intentional, and structural. 

To achieve this, we prioritize **Intentional Asymmetry** and **Tonal Depth**. Instead of centering everything, use the `24 (8.5rem)` spacing tokens to create "power voids"—large areas of whitespace that force the eye toward high-contrast typography. Elements should feel like they are floating in a pressurized, clean environment rather than being locked into a rigid box.

## 2. Colors & Surface Logic
The palette is rooted in absolute blacks and layered grays to create a sophisticated, high-tech executive aesthetic.

### The "No-Line" Rule
**Explicit Instruction:** Prohibit the use of 1px solid borders for sectioning content. Boundaries must be defined solely through background color shifts. For example, a `surface-container-low` (#f3f3f5) section sitting on a `surface` (#f9f9fb) background creates a sophisticated boundary that feels architectural rather than "designed."

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—like stacked sheets of frosted glass or fine stationery.
*   **Base:** `surface` (#f9f9fb)
*   **Sectioning:** `surface-container-low` (#f3f3f5)
*   **Interactive Cards:** `surface-container-lowest` (#ffffff)
*   **Overlays/Modals:** `surface-container-high` (#e8e8ea)

### The Glass & Gradient Rule
To prevent the UI from feeling "flat," use **Glassmorphism** for floating elements (headers, floating action menus). 
*   **Token:** `surface_container_lowest` at 80% opacity with a `20px` backdrop blur.
*   **Signature Textures:** For primary CTAs, use a subtle linear gradient from `primary` (#000000) to `primary_container` (#3b3b3b) at a 145-degree angle. This adds a "weighted" feel to buttons that flat black cannot achieve.

## 3. Typography
We utilize **Inter** with refined metrics to convey authority.

| Level | Token | Size | Tracking | Leading | Weight |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Display** | `display-lg` | 3.5rem | -0.04em | 1.1 | 600 (Bold) |
| **Headline**| `headline-md`| 1.75rem| -0.02em | 1.2 | 500 (Medium) |
| **Title**   | `title-md`   | 1.125rem| -0.01em | 1.4 | 500 (Medium) |
| **Body**    | `body-md`    | 0.875rem| 0 | 1.6 | 400 (Regular) |
| **Label**   | `label-md`   | 0.75rem | +0.05em | 1.0 | 600 (All Caps) |

**Editorial Strategy:** Use `display-lg` sparingly for high-impact statements. Pair it immediately with `body-md` for a high-contrast scale that feels like a premium tech whitepaper.

## 4. Elevation & Depth
Depth is achieved through **Tonal Layering** and **Ambient Light Simulation**.

*   **The Layering Principle:** Avoid shadows for layout. Place a `surface-container-lowest` card on a `surface-container-low` background to create a "soft lift."
*   **Ambient Shadows:** When an element must float (e.g., a dropdown), use an extra-diffused shadow: `0 20px 40px rgba(26, 28, 29, 0.06)`. The shadow color is derived from `on_surface` (#1a1c1d) to ensure it looks like a natural occlusion of light.
*   **The Ghost Border:** If accessibility requires a border, use the `outline_variant` (#c6c6c6) at **15% opacity**. Never use 100% opaque borders.
*   **Glass Depth:** For sidebars or top navigation, use a `1px` inner-stroke of `surface_container_lowest` (#ffffff) to simulate the edge of a glass pane.

## 5. Components

### Buttons
*   **Primary:** Background: `primary` (#000000) to `primary_container` (#3b3b3b) gradient. Text: `on_primary` (#e2e2e2). Corner: `md` (0.375rem).
*   **Secondary:** Background: `surface-container-highest` (#e2e2e4). Text: `on_surface`. No border.
*   **Tertiary:** Text: `secondary` (#5e5e63). Interaction: Becomes `primary` (#000000) on hover with a `0.3s` transition.

### Input Fields
*   **Style:** Minimalist underline or subtle container.
*   **Default State:** `surface-container-low` background, no border, `sm` (0.125rem) radius.
*   **Focus State:** Background shifts to `surface-container-lowest`, with a `1px` "Ghost Border" of `primary`.

### Cards & Lists
*   **Constraint:** Zero dividers. 
*   **Separation:** Use `spacing-6` (2rem) of vertical whitespace between list items. Use a `surface-container-lowest` background to group card content.
*   **Interactive List Items:** On hover, shift background to `surface-container-low`.

### Signature Component: The "Executive Breadcrumb"
Instead of standard "Home > Category," use a high-contrast breadcrumb using `label-sm` in `secondary` (#5e5e63) with a `px` divider, placed with `spacing-12` (4rem) of top margin to give the header room to breathe.

## 6. Do’s and Don'ts

### Do
*   **Do** use asymmetrical margins. A layout that is slightly "off-center" feels more custom and less like a template.
*   **Do** use `letter-spacing` (tracking) for labels. It adds a "technical" feel to the typography.
*   **Do** layer surfaces. A `surface-lowest` item inside a `surface-low` section inside a `surface` page is the gold standard for depth.

### Don’t
*   **Don't** use `#000000` for body text. Use `on_surface` (#1a1c1d) for readability; reserve pure black for primary actions and display type.
*   **Don't** use lines to separate content. If you feel the need for a line, add more whitespace (`spacing-8`) instead.
*   **Don't** use standard "drop shadows." If it looks like a shadow, it’s too dark. It should look like a "glow of darkness."