# budget-tracker
1. Dashboard layout structure

.sidebar (nav menu), .header, and .main with six category cards (Food, Transport, Rent, Entertainment, Savings, Utilities), each with realistic static numbers, a progress bar, and a % change badge.

2. Grid + Flexbox

.dashboard uses CSS Grid (grid-template-columns / grid-template-areas) for the page skeleton.
.card-grid uses Grid with auto-fit, minmax(220px, 1fr) for the card layout.
Flexbox handles the header's internal alignment, the sidebar's nav item stack, and each card's internal content stack — no position: absolute anywhere in the layout.

3. Theme using CSS properties

All colors live in :root (--color-brand, --color-accent, --color-surface, --color-text-primary, --color-text-secondary, plus a few supporting tokens), referenced throughout instead of hardcoded hex values.

4. Making the dashboard responsive

A @media (max-width: 768px) block collapses the grid to a single column, turns the sidebar into a horizontal scroll bar, and stacks the header. Open DevTools → Toggle Device Toolbar and resize through 768px to verify the collapse.

5. Micro-interactions

.card:hover, .card:focus-visible animates transform + box-shadow over 200ms (under the 250ms cap), and cards are tabindex="0" so keyboard focus triggers the same effect.

Stretch goal

A [data-theme="dark"] block overrides only the :root variables — nothing else changes. A small toggle button in the header (with a few lines of JS) flips the attribute so you can preview both themes live; that script is purely for demoing the stretch goal and isn't needed for the CSS requirements themselves.
