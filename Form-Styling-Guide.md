# iZZi Retreats — GHL Experience Intake Form Styling Guide

> **HumAi GoHighLevel Workshop — Part 2 of 2 (Style)**
>
> Prepared by **Rich at HumAi** for members of the HumAi GoHighLevel Workshop. This guide (and its build companion) is part of a series that walks members through building forms, calendars, and websites using GoHighLevel's builder tools. Open this file with the **Markdown Viewer** included in the `0.project-viewer` folder — hex values render as clickable color chips and every code block gets a one-click copy button.
>
> Pair this with: **iZZi Retreats — Experience Intake Form Build Guide** (Part 1). Build the form first, then work through this file to style it.

---

This is the styling pair to the **iZZi Retreats — Experience Intake Form Build Guide**. It turns the raw form you just built into the finished iZZi look: deep-midnight surface, iZZi-gradient submit button, teal focus ring, numbered-serif section headings, and a subtle iZZi halo around the card.

Everything below is grouped by the exact panel name you'll see in the GHL form builder (**Styles** tab and **Advanced** tab). Copy each value straight across — no translation needed.

> **Before you start:** open your form in **Sites → Forms → Builder → iZZi Retreats — Experience Intake → Edit**. Click anywhere on the form canvas (not a field). The right panel opens to **Styles / Themes / Advanced**. That's your workbench for this guide.

---

## Brand palette reference

| Token | Hex (8-digit) | Use |
|---|---|---|
| Background | `#05060FFF` | Outer page |
| Form surface | `#0A0E1FFF` | Form background |
| Surface | `#111630FF` | Input fill |
| Surface elevated | `#1A2047FF` | Hover / active |
| Border | `#1E2544FF` | Input + form border |
| Foreground | `#F3F4FAFF` | Body text |
| Muted foreground | `#8B93B4FF` | Labels, captions, placeholders |
| Caption | `#5D668BFF` | Numbered eyebrow text |
| iZZi teal (primary) | `#5EEAD4FF` | Focus ring, accent, gradient stop |
| iZZi violet | `#A78BFAFF` | Gradient stop |
| iZZi pink | `#F0ABFCFF` | Gradient stop, required asterisk |
| Gold shimmer | `#FBBF24FF` | Signature accent |
| Heading font | `Cormorant Garamond` | Section headings |
| Body font | `Inter` | Labels + inputs |
| Section label font | `Space Grotesk` | Numbered eyebrows |

> Click any hex chip in this document to copy the value.

---

## Styles tab

The three expandable sections on the Styles tab are **Layout**, **Colors & Background**, and **Miscellaneous**. Open them one at a time and match the values below.

### Styles → LAYOUT

| Field | Value |
|---|---|
| Show Image | Off |
| Columns | `One Column` |
| Input Style | `Box` |
| Width | `720` PX |
| Field Spacing | `22` PX |
| Label Width | `160` PX *(ignored when labels are top-aligned)* |
| Label Alignment | Top (middle icon) |
| Margin & Padding → Margin | `auto` |
| Margin & Padding → Padding Top | `56` PX |
| Margin & Padding → Padding Right | `48` PX |
| Margin & Padding → Padding Bottom | `56` PX |
| Margin & Padding → Padding Left | `48` PX |
| Show Label | On |

> **Teaching note — Columns.** GHL offers One Column or Two Column. Two Column packs First Name + Last Name onto a single row on desktop and still stacks on mobile. For this teaching form we stay **One Column** so every field is visually isolated and easier to inspect — swap to Two Column on production forms where you'd like tighter spacing for short paired fields.

### Styles → COLORS & BACKGROUND

| Field | Value |
|---|---|
| Background | `#0A0E1FFF` |
| Primary Color | `#5EEAD4FF` |
| Input Text Color | `#F3F4FAFF` |
| Map Primary color to Button color | ✔ Checked |
| Input Background Color | `#111630FF` |
| Input Border | `#1E2544FF` |
| Background Image | *(leave empty)* |

> **Teaching note — 8-digit hex.** GHL's color inputs accept `#RRGGBBAA` — the last two characters are alpha. `FF` = fully opaque. Use lower alphas like `33` (~20%) for glows and `22` (~13%) for halos. If a picker rejects an 8-digit value, fall back to 6-digit and note it.

### Styles → MISCELLANEOUS

| Field | Value |
|---|---|
| Agency Branding | Off |

---

## Advanced tab

This is where the fine details live — border, shadow, typography, padding, and the Custom CSS block that ties it all together. Five expandable sections: **Form**, **Input Field**, **Label**, **Short Label**, **Placeholder**, plus **Custom CSS** at the bottom.

### Advanced → FORM

| Field | Value |
|---|---|
| Border Width | `1` PX |
| Corner Radius | `4` PX |
| Border Color | `#1E2544FF` |
| Border Style | Solid (first icon) |
| Shadow → Color | `#5EEAD422` *(iZZi-teal halo, ~13% alpha)* |
| Shadow → Horizontal | `0` PX |
| Shadow → Vertical | `0` PX |
| Shadow → Blur | `80` PX |
| Shadow → Spread | `0` PX |

> **Teaching note — Form shadow.** A low-alpha wide-blur shadow reads as a soft *glow* around the card rather than a drop shadow under it. Set Horizontal and Vertical to `0`, bump Blur to 60–100, and choose your accent color with 10–15% alpha. It's the single fastest way to make a form feel premium on a dark background.

### Advanced → INPUT FIELD

| Field | Value |
|---|---|
| Font Color | `#F3F4FAFF` |
| Active Tag Color | `#5EEAD433` *(teal accent, low alpha)* |
| Border Width | `1` PX |
| Border Color | `#1E2544FF` |
| Corner Radius | `4` PX |
| Width | `640` PX |
| Border Style | Solid (first icon) |
| Padding → Top | `14` PX |
| Padding → Right | `16` PX |
| Padding → Bottom | `14` PX |
| Padding → Left | `16` PX |
| Shadow → Color | Default *(leave unset)* |
| Shadow → Horizontal / Vertical / Blur / Spread | `0` PX each |

### Advanced → LABEL

| Field | Value |
|---|---|
| Label Color | `#F3F4FAFF` |
| Font Family | `Inter` |
| Font Size | `14` PX |
| Font Weight | `500` |

### Advanced → SHORT LABEL

| Field | Value |
|---|---|
| Short Label Color | `#8B93B4FF` |
| Font Family | `Inter` |
| Font Size | `12` PX |
| Font Weight | `400` |

> **Teaching note — Short Label.** Short Label is the small helper text that appears *under* a label (or inside compound fields like Full Address to mark Street / City / State / Zip / Country). Muted grey keeps it legible without competing with the main label.

### Advanced → PLACEHOLDER

| Field | Value |
|---|---|
| Placeholder Color | `#8B93B4FF` |
| Font Family | `Inter` |
| Font Size | `14` PX |
| Font Weight | `400` |

---

## Submit button

GHL does not give the submit button its own Advanced panel — you set the button **label** on the element itself, and everything else (gradient, radius, padding, hover glow, typography) happens in the **Custom CSS** block below.

1. Click the **Submit** element on the canvas.
2. In its element panel, set **Button Label** to `Send my vision`.
3. Leave the element panel as-is. The CSS does the rest.

---

## Advanced → CUSTOM CSS

Paste this whole block into the **Custom CSS** editor at the bottom of the Advanced tab. It handles the iZZi-gradient submit button, focus ring, dropdown options on dark, checkbox/radio accents, consent text, required asterisk, signature pad, file upload button, and the native date picker.

```css
/* =========================================================
   iZZi Retreats — Experience Intake Form
   Paste as-is into Advanced → Custom CSS
   ========================================================= */

/* --- Focus ring on all inputs -------------------------- */
.form-builder--item input:focus,
.form-builder--item select:focus,
.form-builder--item textarea:focus,
input.form-control:focus,
textarea.form-control:focus,
select.form-control:focus {
  outline: none !important;
  border-color: #5EEAD4 !important;
  box-shadow: 0 0 0 3px rgba(94, 234, 212, 0.22) !important;
}

/* --- iZZi-gradient submit button --------------------- */
.form-builder--item button[type="submit"],
button.btn-submit,
.form-builder--item .btn-submit {
  background: linear-gradient(120deg, #5EEAD4 0%, #A78BFA 55%, #F0ABFC 100%) !important;
  color: #05060F !important;
  border: none !important;
  border-radius: 9999px !important;
  padding: 16px 40px !important;
  font-family: 'Inter', Arial, sans-serif !important;
  font-size: 15px !important;
  font-weight: 600 !important;
  letter-spacing: 0.02em !important;
  cursor: pointer !important;
  box-shadow: 0 12px 44px -12px rgba(167, 139, 250, 0.65) !important;
  transition: transform 180ms ease-out, box-shadow 180ms ease-out !important;
}

.form-builder--item button[type="submit"]:hover,
button.btn-submit:hover,
.form-builder--item .btn-submit:hover {
  transform: translateY(-2px) !important;
  box-shadow: 0 18px 60px -12px rgba(167, 139, 250, 0.9) !important;
}

/* --- Dropdown option list (native <select>) ------------ */
.form-builder--item select option {
  background-color: #111630 !important;
  color: #F3F4FA !important;
}

/* --- Checkbox + radio accent --------------------------- */
input[type="checkbox"],
input[type="radio"] {
  accent-color: #5EEAD4 !important;
  width: 16px !important;
  height: 16px !important;
}

/* --- Consent / small-print labels ---------------------- */
.form-builder--item .form-check-label,
.form-builder--item [data-type="checkbox"] label {
  font-family: 'Inter', Arial, sans-serif !important;
  font-size: 12px !important;
  color: #8B93B4 !important;
  line-height: 1.6 !important;
}

/* --- Required-field asterisk (iZZi pink) ------------- */
.form-builder--item .required-asterisk,
.form-builder--item label .required {
  color: #F0ABFC !important;
  margin-left: 3px !important;
}

/* --- Inline links inside labels (consent etc.) --------- */
.form-builder--item a {
  color: #5EEAD4 !important;
  text-decoration: underline !important;
  text-underline-offset: 2px !important;
  transition: color 150ms ease !important;
}
.form-builder--item a:hover {
  color: #A78BFA !important;
}

/* --- File Upload button -------------------------------- */
.form-builder--item input[type="file"]::-webkit-file-upload-button,
.form-builder--item input[type="file"]::file-selector-button {
  background-color: #1A2047 !important;
  color: #F3F4FA !important;
  border: 1px solid #1E2544 !important;
  padding: 8px 16px !important;
  border-radius: 9999px !important;
  font-family: 'Inter', Arial, sans-serif !important;
  font-size: 13px !important;
  font-weight: 500 !important;
  cursor: pointer !important;
  margin-right: 12px !important;
  transition: background 150ms ease, border-color 150ms ease !important;
}
.form-builder--item input[type="file"]::-webkit-file-upload-button:hover,
.form-builder--item input[type="file"]::file-selector-button:hover {
  background-color: #232C5A !important;
  border-color: #5EEAD4 !important;
}

/* --- Native date picker on dark ------------------------ */
.form-builder--item input[type="date"]::-webkit-calendar-picker-indicator {
  filter: invert(0.9) hue-rotate(150deg) saturate(1.2);
  cursor: pointer;
}

/* --- Number field spinners (tone them down) ------------ */
.form-builder--item input[type="number"]::-webkit-inner-spin-button,
.form-builder--item input[type="number"]::-webkit-outer-spin-button {
  opacity: 0.4;
}

/* --- Signature pad (contrast against dark) ------------- */
.form-builder--item .signature-pad,
.form-builder--item canvas.signature {
  background: #111630 !important;
  border: 1px dashed #1E2544 !important;
  border-radius: 4px !important;
}
.form-builder--item .signature-pad:hover,
.form-builder--item canvas.signature:hover {
  border-color: #FBBF24 !important;
}

/* --- Text List field (add-another pill + rows) --------- */
.form-builder--item .text-list-row input {
  background: #111630 !important;
  border: 1px solid #1E2544 !important;
  color: #F3F4FA !important;
}
.form-builder--item .text-list-add,
.form-builder--item button.add-row {
  background: transparent !important;
  color: #5EEAD4 !important;
  border: 1px dashed #5EEAD4 !important;
  border-radius: 9999px !important;
  padding: 6px 14px !important;
  font-size: 13px !important;
  font-weight: 500 !important;
  cursor: pointer !important;
}
.form-builder--item .text-list-add:hover {
  background: rgba(94, 234, 212, 0.1) !important;
}

/* --- Custom HTML section heading polish --------------- */
.form-builder--item h2 {
  letter-spacing: -0.01em !important;
}

/* --- Captcha sits nicely on dark ---------------------- */
.form-builder--item .g-recaptcha,
.form-builder--item .grecaptcha-badge {
  border-radius: 8px !important;
}

/* --- Thank-you message styling ------------------------ */
.form-builder--thank-you,
.thank-you-message {
  background: #0A0E1F !important;
  color: #F3F4FA !important;
  border: 1px solid #1E2544 !important;
  border-radius: 4px !important;
  padding: 40px !important;
  font-family: 'Cormorant Garamond', Georgia, serif !important;
  font-size: 22px !important;
  line-height: 1.45 !important;
  text-align: center !important;
}
```

> **Teaching note — why Custom CSS is needed at all.** The Styles panel covers the 20% of things most clients care about — background, primary, border, typography. Everything else (gradient buttons, hover states, dropdown option colors, accent-color on checkboxes, styling the file upload button, taming the native date picker) lives in Custom CSS. If a selector doesn't catch, **right-click the live form in an incognito window, Inspect, and grab the class name GHL actually rendered** — then add or tweak the selector.

---

## What each change actually does

A quick cross-reference so you can see which panel value maps to which visual outcome. Use this when troubleshooting — if something looks wrong, this table tells you where to go back and fix it.

| Visual element | Where it's controlled |
|---|---|
| Form background | Styles → Colors & Background → Background |
| Form card border + radius | Advanced → Form → Border Width / Corner Radius / Border Color |
| Form halo glow | Advanced → Form → Shadow |
| Input pill colour | Styles → Colors & Background → Input Background Color |
| Input text | Styles → Colors & Background → Input Text Color |
| Input border | Styles → Colors & Background → Input Border |
| Input corner radius | Advanced → Input Field → Corner Radius |
| Input padding | Advanced → Input Field → Padding |
| Field spacing (rows) | Styles → Layout → Field Spacing |
| Label font + color | Advanced → Label |
| Helper text under label | Advanced → Short Label |
| Placeholder text | Advanced → Placeholder |
| Focus ring on active input | Custom CSS (first block) |
| Submit gradient + glow | Custom CSS (submit block) |
| Dropdown option colors | Custom CSS (`select option`) |
| Checkbox / radio fill | Custom CSS (`accent-color`) |
| Required red asterisk | Custom CSS (`.required-asterisk`) |
| File upload button | Custom CSS (`::file-selector-button`) |
| Signature pad surface | Custom CSS (`.signature-pad`) |
| Section headings (numbered + serif) | The Custom HTML blocks in the Build Guide (not styled via panels) |

---

## Test checklist after styling

1. **Preview** the form and scroll top-to-bottom. Compare against the palette above — every surface, border, text color should feel like it belongs on the same page.
2. **Tab through** every field. The focus ring should be a soft teal glow (`#5EEAD422`) — not the browser default.
3. **Hover the submit button.** It should lift 2px and the violet glow should intensify.
4. **Open a Dropdown** — options should render on `#111630` with light text. (Chrome/Edge honour `select option` CSS; Safari sometimes ignores it — note the fallback if a client uses Safari.)
5. **Check a checkbox / radio.** The fill color should be iZZi teal.
6. **Upload a file.** The *Choose file* button should be the pill-shaped dark button with a teal border on hover.
7. **Draw a signature.** The pad background should be `#111630` with a dashed border that turns gold on hover.
8. **Trigger a required field** (leave a required input blank and hit submit). The asterisk should read iZZi pink.
9. **Open the form on mobile.** Width collapses to 100%, padding tightens, submit button stays centred. If anything breaks, use a media query inside the Custom CSS block.
10. **Cross-browser pass:** Chrome, Safari, Firefox. At minimum verify focus ring + submit gradient render correctly in all three.

> **If a selector didn't catch:** right-click the element in the live (embedded) form, copy the class name, and add a matching rule at the bottom of the Custom CSS block. GHL frequently renames these classes between releases — when that happens, you only have to update the selectors, not redo the whole guide.
