# My Budget Tracker — Week 3 Build

A personal budget and expense tracker, built progressively over 8 weeks.
This is the **Week 3** snapshot: the same structure and content as Week 2,
now refined with an intentional color palette, custom typography, and a
considered use of the CSS Box Model to create distinct card-like sections.

## Files

- `index.html` — page structure (only change from Week 2: added Google Fonts links)
- `style.css` — full visual design pass
- `README.md` — this file

## What was done this week

No new HTML structure or functionality was added — every change is visual.

### 1. Color Palette

A cohesive, restrained palette built around green as the primary color, with
ivory as the page background and a coral accent reserved for attention.

| Role | Token | Value |
|------|-------|-------|
| Headings | `--green-900` | `#14532d` |
| Primary (buttons, table header) | `--green-700` | `#15803d` |
| Accent (borders, focus ring) | `--green-500` | `#22c55e` |
| Soft green (zebra, tinted bg) | `--green-100` | `#dcfce7` |
| Page background | `--ivory` | `#fbfaf6` |
| Card background | `--white` | `#ffffff` |
| Body text | `--ink-900` | `#0f172a` |
| Muted text | `--ink-700` | `#334155` |

All colors are declared once as CSS custom properties in `:root`, then
reused everywhere. Change one token — the whole app updates.

### 2. Typography

Two Google Fonts form a clear visual hierarchy:

- **Plus Jakarta Sans** — headings (`h1`, `h2`), button labels, table headers.
  A modern geometric sans with confident weight, used at 700–800.
- **Inter** — body text, labels, inputs, table cells. A neutral,
  highly legible sans designed for UI.

Fonts are loaded via `<link>` tags in the `<head>` with `preconnect` hints
for faster loading, and `display=swap` so text shows immediately while the
font downloads.

### 3. Table and Form Styling

- **Table:** green header row with uppercase letter-spaced labels,
  comfortable 14×16px cell padding, subtle bottom borders, zebra striping
  via `:nth-child(even)`, and hover highlighting on rows.
- **Form:** 12×14px input padding, 1.5px borders, rounded corners,
  a green focus ring using `box-shadow`, and a prominent green button
  with its own hover and active states.
- **Consistency:** all inputs, selects, and the button share the same
  border-radius scale (`--radius-md: 10px`).

### 4. CSS Box Model

Each section is styled as a distinct visual **card**:

| Section | Border treatment | Shadow | Radius |
|---------|-----------------|--------|--------|
| `#main-header` | gradient, no border | `--shadow-card` | `--radius-lg` |
| `.add-expense` | 1px border + 4px top accent | `--shadow-card` | `--radius-lg` |
| `.expenses-section` | 1px border + 4px top accent | `--shadow-card` | `--radius-lg` |
| `.help-section` | 1px border | `--shadow-card` | `--radius-lg` |
| `.video-section` | 1px border + 4px top accent | `--shadow-card` | `--radius-lg` |

- **Margin** separates every card (`28px` between sections).
- **Padding** creates internal breathing room (`28px 26px` per card).
- **Borders** define each section's boundary.
- **Border-radius** softens the entire interface.

A global `box-sizing: border-box` rule at the top keeps all padding and
borders inside the declared widths — no more surprise overflows.

### 5. Advanced Selectors (carried from Week 2)

All five advanced selectors remain in place and are now doing visual work:

1. **Focus state** — `input:focus, select:focus` → green focus ring
2. **Negation** — `input:not([type="button"]):hover` → hover borders
3. **Direct child** — `form > button` → primary button styling
4. **Positional** — `.expenses-table tbody tr:nth-child(even)` → zebra rows
5. **Descendant** — `.expenses-section td` → muted table text

## What's coming next

- **Week 4–5:** Layout — CSS Grid for the overall page, responsive refinements
- **Week 6:** JavaScript — read form values and render expenses dynamically
- **Week 7:** Add Expense button wired up
- **Week 8:** Totals, category breakdown, edit/delete, final polish

## How to run it

1. Download or clone the repository
2. Open `index.html` in any modern browser
3. No build step, no dependencies — fonts load from Google's CDN
