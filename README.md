# SpendWise Dashboard Shell (Week 4)

The visual foundation of my SpendWise budgeting app. This week is layout only: a responsive
dashboard built with CSS Grid and Flexbox, using realistic static content. There is no
functionality yet.

## What I built

### index.html
- **Sidebar** (`<aside>` with a `<nav>`): logo, five navigation links (Dashboard is marked active) and a note.
- **Header** (`<header>`): page title, month subtitle, an "Add expense" button and an avatar.
- **Main content** (`<main>`):
  - A summary row with total budget, amount spent and amount remaining.
  - Six category cards (`<article>`): Food, Transport, Rent, Entertainment, Savings and Utilities.
    Each card shows the category, a status badge, the amount spent, a progress bar and the budget.
  - The cards have `tabindex="0"` so they can be reached with the keyboard.

### style.css
- **Theme with CSS custom properties** on `:root`: brand, accent, surface, text and secondary text
  colors (plus a few helpers for borders, shadow and radius). Colors across the stylesheet come from these variables.
- **CSS Grid** for the overall page layout (`grid-template-areas`: sidebar, header, content), and for the grid of category cards.
- **Flexbox** for the header, the sidebar and its nav items, the summary row, and the inside of every card.
- **No absolute positioning** is used for layout.
- **Responsive design**: a `@media (max-width: 767px)` query collapses the page to a single column
  (sidebar on top, then header, then content) and the cards to one column. Verified with the
  DevTools Device Toolbar.
- **Card micro-interactions**: on hover and keyboard focus the card lifts with `transform: translateY(-4px)`
  and gains a larger `box-shadow`. The transition lasts 200ms. A `prefers-reduced-motion` rule turns it off for people who ask for less motion.
- **Dark theme (stretch goal)**: a `@media (prefers-color-scheme: dark)` block that overrides only the `:root` variables.

## How to run
Open `index.html` in a browser. Keep `index.html` and `style.css` in the same folder.
An internet connection is needed to load the Manrope font from Google Fonts.

## How I tested
- Resized the browser and used DevTools Device Toolbar to confirm the single-column layout below 768px.
- Pressed Tab to confirm each card shows the lift animation and a focus outline.
- Switched the operating system to dark mode to confirm the dark theme.
