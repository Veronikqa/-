# Design System Strategy: The Grandmaster’s Editorial

## 1. Overview & Creative North Star
**Creative North Star: The Monolith Strategy**

This design system is not a mere utility; it is an intellectual environment. Inspired by the tactical precision of a Grandmaster’s opening and the stark, high-contrast landscape of the chessboard, the system rejects the "bubbly" softness of modern SaaS. Instead, it embraces **The Monolith Strategy**: a visual language defined by uncompromising geometry, razor-sharp edges, and an editorial layout that feels like a premium collector's journal.

We break the "template" look through **Calculated Asymmetry**. By utilizing a rigid 8-column or 12-column grid—reminiscent of the board—we allow elements to span across specific coordinates, leaving intentional white space (voids) that command focus. This is a system for deep work, quiet study, and the celebration of the game’s heritage.

## 2. Colors & Surface Architecture
The palette is a binary dialogue between absolute light and absolute dark, mediated by a sophisticated range of greys.

*   **Primary (`#000000`) & On-Primary (`#FFFFFF`):** These represent the "Black" and "White" pieces. They are the only colors used for high-impact communication.
*   **The "No-Line" Rule:** To maintain an elite editorial feel, **1px solid borders are strictly prohibited** for sectioning. Structural boundaries must be defined exclusively through background color shifts. For instance, a `surface-container-low` (`#f3f3f3`) sidebar sitting against a `surface` (`#f9f9f9`) main stage creates a sophisticated, "borderless" division.
*   **Surface Hierarchy & Nesting:** Treat the UI as a physical stack of fine paper. 
    *   Use `surface-container-lowest` (`#ffffff`) for primary content cards.
    *   Place them on a `surface-container` (`#eeeeee`) background to create a subtle "lift."
    *   Nesting should never exceed three levels of tonal shift.
*   **The "Ink & Parchment" Gradient:** While the UI is minimalist, use a subtle linear gradient on primary CTAs—moving from `primary` (#000000) to `primary_container` (#3b3b3b). This adds a "weighted" feel to the buttons, making them appear like physical obsidian tiles rather than flat digital boxes.

## 3. Typography: The Editorial Voice
Typography is the primary vehicle for the brand’s intellectual tone. We pair the authoritative tradition of a serif with the clinical precision of a modern sans-serif.

*   **Display & Headlines (Noto Serif):** Used for titles and intellectual anchors. These should be set with tighter letter-spacing (-0.02em) to feel like a high-end publication. `display-lg` (3.5rem) should be used sparingly to create "hero moments" that mimic the opening page of a chess manual.
*   **Body & Labels (Inter):** The "Modern Workhorse." Inter provides a neutral, high-readability counterpoint to the serif. All body text should utilize `body-md` or `body-lg` to ensure the "intellectual" mood doesn't sacrifice accessibility.
*   **The Hierarchy Rule:** Never mix the two families within the same line. Headlines are always Serif (Tradition); UI labels, data, and metadata are always Sans-Serif (Modernity).

## 4. Elevation & Depth: Tonal Layering
In this system, "Elevation" does not mean "Shadow." We use the Material surface tokens to create depth through color density.

*   **The Layering Principle:** Rather than using a drop shadow to "lift" a card, use a `surface-container-highest` (`#e2e2e2`) background for the container to distinguish it from a `surface` (`#f9f9f9`) page.
*   **Ambient Shadows (The Exception):** If a floating element (like a modal or a piece-promotion popover) requires a shadow, it must be an **Ambient Shadow**: Blur: 40px, Spread: 0, Opacity: 6% of the `on-surface` color. It should feel like a soft glow of light, not a harsh silhouette.
*   **Ghost Borders:** For interactive elements like input fields, use a "Ghost Border": the `outline-variant` token at **15% opacity**. This provides just enough affordance for the user without cluttering the grid with lines.

## 5. Components

### Buttons: The Obsidian Tiles
*   **Primary:** Sharp corners (`0px`), Black background (`primary`), White text (`on-primary`). 
*   **Secondary:** Sharp corners (`0px`), `outline` border (Ghost Border style), Black text.
*   **Behavior:** On hover, the primary button should shift to `primary_fixed` (#5e5e5e), mimicking the physical darkening of a stone when touched.

### Cards: The Grid Blocks
*   **Structure:** No borders. No shadows. Use `surface-container-lowest` for the card body.
*   **Grid Alignment:** All cards must snap to the `8px` spacing scale. A card's internal padding should be a minimum of `16` (4rem) to provide the luxury of "breathing room."

### Inputs & Fields
*   **Styling:** Sharp `0px` corners. Use `surface-container-high` for the input background to create a "recessed" look.
*   **Focus State:** The border transitions from 0% opacity to 100% `primary` (#000000) with a 2px stroke.

### Specialized Chess Components
*   **The Board Grid:** The board must use `on-surface` (#1a1c1c) for dark squares and `surface-container-lowest` (#ffffff) for light squares. 
*   **Notation Lists:** Use `label-md` for move notation. Alternate background colors for rows (`surface` and `surface-container-low`) instead of using divider lines.

## 6. Do's and Don'ts

### Do:
*   **Use the Grid as a Weapon:** Align text to the same vertical axis as your primary images to create a strong "Redline."
*   **Embrace the Void:** Use the `20` (5rem) and `24` (6rem) spacing tokens between sections to emphasize the "Minimalist" mood.
*   **Focus on Contrast:** Ensure all "On-Surface" text meets at least 7:1 contrast ratios. Intellectualism requires clarity.

### Don't:
*   **No Rounding:** Never use `border-radius`. A single rounded corner breaks the "Monolith" illusion.
*   **No Decorative Dividers:** If you feel the need to add a line to separate content, try adding `32px` of vertical space instead.
*   **No "Generic" Blue:** Avoid any color outside the defined black/white/grey spectrum unless it is the `error` token (#ba1a1a) for illegal moves.