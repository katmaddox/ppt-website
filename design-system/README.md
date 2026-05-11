# Practice Transition Partners — Design Tokens

## Files

| File | Purpose |
|---|---|
| `tokens.json` | Design tokens — import into Figma via Tokens Studio |
| `tokens.css` | Same tokens as CSS custom properties — ready for web dev |
| `index.html` | Living style guide — open in browser to preview all components |

---

## For the Designer — Figma Setup

1. Install the **Tokens Studio for Figma** plugin (free)  
   → [tokenstudio.io](https://tokenstudio.io)

2. Open the plugin → **Load** → **JSON** → paste or upload `tokens.json`

3. Apply the `global` set first, then `typography`, then `semantic`

4. The `semantic` layer uses references (e.g. `{global.color.navy}`) so changing a base color cascades everywhere automatically

**Fonts to install in Figma:**
- Playfair Display (display/headings) — available on Google Fonts
- Inter (body/UI) — available on Google Fonts

---

## For the Developer — CSS Variables

The `tokens.css` file maps every token to a CSS custom property.

```css
/* Example usage */
.my-heading {
  font-family: var(--font-display);
  color: var(--color-navy);
  font-size: var(--text-4xl);
}
```

Or run **Style Dictionary** to generate platform-specific outputs (iOS Swift, Android XML, JS/TS constants):

```bash
npx style-dictionary build --config style-dictionary.config.json
```

---

## Token Structure

```
global/          ← raw values (colors, sizes, font names)
  color/
  fontFamilies/
  fontSizes/
  fontWeights/
  lineHeights/
  letterSpacing/
  spacing/
  borderRadius/
  boxShadow/

typography/      ← composite type styles (reference global tokens)
  h1, h2, h3, h4
  eyebrow, label
  body-lg, body, body-sm, caption
  pullquote, kpi
  nav-link, btn, btn-sm

semantic/        ← role-based aliases (reference global tokens)
  text/          ← heading, body, muted, link, accent, inverted
  bg/            ← page, surface, subtle, dark, accent
  border/        ← default, strong, focus, accent
  button/        ← primary, secondary, accent variants
  portal/        ← sidebar, topbar, content area colors
  status/        ← active, warning, error, draft badge colors
```

---

## Color Palette

| Token | Hex | Use |
|---|---|---|
| `--color-navy` | `#022C51` | Primary brand, headings, nav, dark sections |
| `--color-royal` | `#115694` | Secondary primary, hover states, links |
| `--color-gray` | `#73716C` | Body text, borders, muted UI |
| `--color-cream` | `#FAF8F1` | Page background |
| `--color-blue` | `#1D86E4` | Accent, interactive, info states |
| `--color-gold` | `#ECB100` | Logo star, featured badges, pullquotes, CTA accent |

---

## Note on Logo

The compass star logo shown in the style guide is sourced from the client's brand exploration PDF. **Client confirmation is still pending.** Do not use in final production until approved.
