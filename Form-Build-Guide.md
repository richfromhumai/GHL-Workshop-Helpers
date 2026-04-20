# iZZi Retreats — GHL Experience Intake Form Build Guide

> **HumAi GoHighLevel Workshop — Part 1 of 2 (Build)**
>
> Prepared by **Rich at HumAi** for members of the HumAi GoHighLevel Workshop. This guide (and its styling companion) is part of a series that walks members through building forms, calendars, and websites using GoHighLevel's builder tools. Open this file with the **Markdown Viewer** included in the `0.project-viewer` folder so code blocks, hex swatches, and copy buttons all render the way they were designed to.
>
> Pair this with: **iZZi Retreats — Experience Intake Form Styling Guide** (Part 2).

---

A teaching form built to expose you to **every GHL form field type at least once**. The example project is **iZZi Retreats**, a fictional luxury wellness & adventure retreat brand — you'll build the intake form its concierge team uses to collect a guest's travel dates, party size, dietary needs, budget, inspiration images, and signature.

By the end of this guide your form will contain:

- All six **standard contact fields** (First Name, Last Name, Email, Phone, Date of Birth, Company Name)
- The **compound Full Address** field
- Every **custom field type** GHL offers — Single Line, Multi-Line, Number, Phone, Email, Monetary, Dropdown, Multiple Options (checkboxes), Radio, Date Picker, Text List, File Upload, Signature, single Checkbox
- Every **form element** — Custom HTML, Captcha, hidden Source, Submit

Once it's built, pair it with the **iZZi Retreats — Experience Intake Form Styling Guide** to theme it.

Open GHL: **Sites → Forms → Builder → + Add Form → Blank Form**. Name it **iZZi Retreats — Experience Intake**.

---

## Brand palette reference

| Token | Hex (8-digit) | Use |
|---|---|---|
| Background | `#05060FFF` | Outer page |
| Form surface | `#0A0E1FFF` | Form background |
| Surface | `#111630FF` | Input fill |
| Surface elevated | `#1A2047FF` | Hover / active row |
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

---

## Form settings

- **Form name:** iZZi Retreats — Experience Intake
- **On Submit:** Show thank-you message (inline)
- **Thank-you message:**
  > Your retreat vision is with us. An iZZi Retreats concierge will reach out within one business day at the email and phone number you shared.
- **Redirect URL:** *(leave blank — inline thank you only)*

> **Teaching note.** GHL gives you three On-Submit behaviours: *Show thank-you message*, *Redirect to URL*, and *Redirect via query parameter*. For intake forms we almost always use the inline thank-you so the guest stays on your site.

---

## Custom Fields — create these first

GHL has two buckets of fields in the form builder: **Standard Fields** (already wired to the contact record — First Name, Last Name, Email, Phone, Full Name, Full Address, Date of Birth, Company Name) and **Custom Fields** you create yourself. Create every custom field below under **Settings → Custom Fields → + Add Field** before you start dragging things onto the canvas.

| Field key (Unique Key) | Type | Notes |
|---|---|---|
| `preferred_name` | Single Line | What they'd like the concierge to call them |
| `alternate_email` | Email | Second email (e.g. assistant's) |
| `work_phone` | Phone | Secondary phone |
| `party_size` | Number | How many travellers total |
| `companion_names` | Text List | Each companion's first name (separate entries) |
| `retreat_type` | Dropdown (Single Option) | Type of retreat |
| `intensity_level` | Radio | Experience intensity |
| `services_of_interest` | Multiple Options | Checkbox group — multi-select |
| `preferred_start_date` | Date Picker | Arrival |
| `preferred_end_date` | Date Picker | Departure |
| `wellness_goals` | Multi Line | Free text |
| `dietary_notes` | Multi Line | Free text |
| `accessibility_needs` | Multi Line | Free text |
| `per_person_budget` | Monetary | USD |
| `total_budget` | Monetary | USD |
| `inspiration_files` | File Upload | Mood board, PDFs, references |
| `medical_form_file` | File Upload | Optional signed waiver |
| `lead_source` | Dropdown | How they heard about us |
| `referrer_name` | Single Line | Conditional on lead_source |
| `guest_signature` | Signature | Digital signature |
| `sms_consent` | Checkbox | Carrier-compliant text |
| `privacy_ack` | Checkbox | Privacy + terms |

> **Teaching note — Unique Keys.** The Unique Key is what you reference in workflows, merge tags, and conditional logic. Keep it lowercase with underscores, no spaces. Once a custom field has data on real contacts, renaming its key will break any workflow that references it — decide the key up front.

---

## Fields to add (in order)

Each section begins with a **Custom HTML** element that renders a numbered eyebrow + serif heading — those are the visual separators between logical groups on the form. Then the actual GHL fields in order.

### Section 1 — Who you are *(Standard contact fields)*

**Custom HTML block** (drag a *Custom HTML* element onto the canvas, open it, paste this into the HTML editor):

```html
<div style="margin:0 0 12px 0;">
  <div style="font-family:'Space Grotesk',Arial,sans-serif;font-size:12px;letter-spacing:0.26em;text-transform:uppercase;color:#5D668B;">01 / Identity</div>
  <h2 style="font-family:'Cormorant Garamond',Georgia,serif;font-size:36px;font-weight:500;color:#F3F4FA;margin:6px 0 6px 0;letter-spacing:-0.01em;">Who you are</h2>
  <p style="font-family:'Inter',Arial,sans-serif;font-size:14px;color:#8B93B4;margin:0;">The basics, so a concierge can reach you.</p>
</div>
```

1. **First Name** — *Standard Field → First Name* — required, placeholder `First name`
2. **Last Name** — *Standard Field → Last Name* — required, placeholder `Last name`
3. **Preferred name** — *Custom Field → Single Line → `preferred_name`* — not required, placeholder `What should we call you?`
4. **Email** — *Standard Field → Email* — required, placeholder `you@domain.com`
5. **Alternate email** — *Custom Field → Email → `alternate_email`* — not required, placeholder `assistant@domain.com (optional)`
6. **Phone** — *Standard Field → Phone* — required, placeholder `(555) 555-5555`
7. **Work phone** — *Custom Field → Phone → `work_phone`* — not required, placeholder `Direct line (optional)`
8. **Date of Birth** — *Standard Field → Date of Birth* — required (some retreats are 21+ or 50+)
9. **Company / Organization** — *Standard Field → Company Name* — not required, placeholder `For corporate retreats`

> **Teaching note — Standard vs Custom.** Always prefer a **Standard Field** when one exists (Email, Phone, First Name, etc.). They auto-map to the contact record and play nicely with workflows, email merges, and the SMS channel. Custom Fields are for everything GHL doesn't already track.

### Section 2 — Where we'll send things *(Compound Address field)*

**Custom HTML block:**

```html
<div style="margin:32px 0 12px 0;">
  <div style="font-family:'Space Grotesk',Arial,sans-serif;font-size:12px;letter-spacing:0.26em;text-transform:uppercase;color:#5D668B;">02 / Address</div>
  <h2 style="font-family:'Cormorant Garamond',Georgia,serif;font-size:36px;font-weight:500;color:#F3F4FA;margin:6px 0 6px 0;letter-spacing:-0.01em;">Where we'll send your welcome kit</h2>
  <p style="font-family:'Inter',Arial,sans-serif;font-size:14px;color:#8B93B4;margin:0;">iZZi Retreats ships a hand-packed welcome box before every trip.</p>
</div>
```

10. **Full Address** — *Standard Field → Full Address* — required.

> **Teaching note — Full Address.** Full Address is a single *compound* element that renders five sub-inputs in one row: Street, City, State / Province, Postal Code, Country. Drag it in once; GHL auto-maps each sub-field to the matching Standard contact property. Don't try to rebuild this with five Single Line fields — you'll lose the contact mapping.

### Section 3 — Retreat preference *(Dropdown, Radio, Number, Text List)*

**Custom HTML block:**

```html
<div style="margin:32px 0 12px 0;">
  <div style="font-family:'Space Grotesk',Arial,sans-serif;font-size:12px;letter-spacing:0.26em;text-transform:uppercase;color:#5D668B;">03 / Preference</div>
  <h2 style="font-family:'Cormorant Garamond',Georgia,serif;font-size:36px;font-weight:500;color:#F3F4FA;margin:6px 0 6px 0;letter-spacing:-0.01em;">The shape of your trip</h2>
  <p style="font-family:'Inter',Arial,sans-serif;font-size:14px;color:#8B93B4;margin:0;">Pick one retreat direction, then tell us who's coming.</p>
</div>
```

11. **Retreat type** — *Custom Field → Dropdown → `retreat_type`* — required. Options:
    - `Wellness & spa`
    - `Adventure & expedition`
    - `Creative & writing`
    - `Silent / meditation`
    - `Corporate offsite`

12. **Experience intensity** — *Custom Field → Radio → `intensity_level`* — required. Options:
    - `Gentle — I'm here to restore`
    - `Balanced — some activity, some rest`
    - `Intensive — push me`

13. **Party size** — *Custom Field → Number → `party_size`* — required. Placeholder `2`. Min `1`, Max `24`.

14. **Companion first names** — *Custom Field → Text List → `companion_names`* — not required. Label: `Companion first names`. Help text: *Add one name per entry — tap the + to add another companion.*

> **Teaching note — Text List.** Text List stores an array of short strings on a single contact field. Use it when the user has to enter 2–N similar items (companion names, team members, children's ages). It's different from Multi-Line, which is one long paragraph.

### Section 4 — Dates *(Date Picker × 2)*

**Custom HTML block:**

```html
<div style="margin:32px 0 12px 0;">
  <div style="font-family:'Space Grotesk',Arial,sans-serif;font-size:12px;letter-spacing:0.26em;text-transform:uppercase;color:#5D668B;">04 / Dates</div>
  <h2 style="font-family:'Cormorant Garamond',Georgia,serif;font-size:36px;font-weight:500;color:#F3F4FA;margin:6px 0 6px 0;letter-spacing:-0.01em;">When you'd like to travel</h2>
</div>
```

15. **Preferred start date** — *Custom Field → Date Picker → `preferred_start_date`* — required.
16. **Preferred end date** — *Custom Field → Date Picker → `preferred_end_date`* — required.

### Section 5 — Services of interest *(Multiple Options / checkbox group)*

**Custom HTML block:**

```html
<div style="margin:32px 0 12px 0;">
  <div style="font-family:'Space Grotesk',Arial,sans-serif;font-size:12px;letter-spacing:0.26em;text-transform:uppercase;color:#5D668B;">05 / Services</div>
  <h2 style="font-family:'Cormorant Garamond',Georgia,serif;font-size:36px;font-weight:500;color:#F3F4FA;margin:6px 0 6px 0;letter-spacing:-0.01em;">Tick everything you'd love</h2>
  <p style="font-family:'Inter',Arial,sans-serif;font-size:14px;color:#8B93B4;margin:0;">Nothing's locked in — we'll curate a shortlist based on what you pick.</p>
</div>
```

17. **Services of interest** — *Custom Field → Multiple Options → `services_of_interest`* — required. Options:
    - `Private chef & nutrition`
    - `Yoga & breathwork`
    - `Guided hiking`
    - `Ice baths & sauna`
    - `Equine therapy`
    - `Sound baths`
    - `Stargazing & astrophotography`
    - `Creative workshops`
    - `Executive coaching`
    - `Spa & bodywork`

> **Teaching note — Radio vs Dropdown vs Multiple Options.** They look similar in the field picker — don't confuse them. **Radio** = one answer, all choices visible. **Dropdown** = one answer, choices hidden until clicked. **Multiple Options** = zero-to-many answers, all visible as checkboxes. Use Radio for short lists (2–5), Dropdown for long lists (6+), Multiple Options when more than one can be true.

### Section 6 — Wellness profile *(Multi-Line textareas, File Upload)*

**Custom HTML block:**

```html
<div style="margin:32px 0 12px 0;">
  <div style="font-family:'Space Grotesk',Arial,sans-serif;font-size:12px;letter-spacing:0.26em;text-transform:uppercase;color:#5D668B;">06 / Profile</div>
  <h2 style="font-family:'Cormorant Garamond',Georgia,serif;font-size:36px;font-weight:500;color:#F3F4FA;margin:6px 0 6px 0;letter-spacing:-0.01em;">Your wellness profile</h2>
  <p style="font-family:'Inter',Arial,sans-serif;font-size:14px;color:#8B93B4;margin:0;">Held in confidence — only the lead concierge and your on-retreat team see this.</p>
</div>
```

18. **Wellness goals** — *Custom Field → Multi Line → `wellness_goals`* — not required. Placeholder `e.g. reset sleep, train for a 50k, unplug from work completely, finish the first draft.`
19. **Dietary notes** — *Custom Field → Multi Line → `dietary_notes`* — not required. Placeholder `Allergies, preferences, religious / cultural requirements.`
20. **Accessibility or mobility needs** — *Custom Field → Multi Line → `accessibility_needs`* — not required. Placeholder `Anything our team must plan around.`
21. **Upload medical / waiver form** — *Custom Field → File Upload → `medical_form_file`* — not required. Max files `1`, max size `10 MB`. Accept `.pdf,.jpg,.png`. Help text: *Optional — only required for expedition retreats.*

### Section 7 — Investment *(Monetary)*

**Custom HTML block:**

```html
<div style="margin:32px 0 12px 0;">
  <div style="font-family:'Space Grotesk',Arial,sans-serif;font-size:12px;letter-spacing:0.26em;text-transform:uppercase;color:#5D668B;">07 / Investment</div>
  <h2 style="font-family:'Cormorant Garamond',Georgia,serif;font-size:36px;font-weight:500;color:#F3F4FA;margin:6px 0 6px 0;letter-spacing:-0.01em;">What you're ready to invest</h2>
  <p style="font-family:'Inter',Arial,sans-serif;font-size:14px;color:#8B93B4;margin:0;">USD. We quote a single all-inclusive number — no hidden extras.</p>
</div>
```

22. **Per-person budget** — *Custom Field → Monetary → `per_person_budget`* — required. Placeholder `5000`.
23. **Total party budget** — *Custom Field → Monetary → `total_budget`* — not required. Placeholder `Leave blank to use per-person × party size.`

> **Teaching note — Monetary.** The Monetary field stores a number with a currency symbol and is locale-formatted on display. It's distinct from Number — workflows and merge tags treat it like currency, which matters if you pipe the value into an invoice or quote email.

### Section 8 — Inspiration *(File Upload)*

**Custom HTML block:**

```html
<div style="margin:32px 0 12px 0;">
  <div style="font-family:'Space Grotesk',Arial,sans-serif;font-size:12px;letter-spacing:0.26em;text-transform:uppercase;color:#5D668B;">08 / Inspiration</div>
  <h2 style="font-family:'Cormorant Garamond',Georgia,serif;font-size:36px;font-weight:500;color:#F3F4FA;margin:6px 0 6px 0;letter-spacing:-0.01em;">Show us what you're picturing</h2>
  <p style="font-family:'Inter',Arial,sans-serif;font-size:14px;color:#8B93B4;margin:0;">Drop a mood board, screenshots of places you've pinned, sample itineraries — anything.</p>
</div>
```

24. **Inspiration files** — *Custom Field → File Upload → `inspiration_files`* — not required. Max files `10`, max size `10 MB` each. Accept `.jpg,.jpeg,.png,.heic,.pdf`.

> **Teaching note — File Upload caps.** Each File Upload field has its own Max Files / Max Size limit, set on the field itself. The GHL account ceiling is 25 MB per file regardless of what you configure here — warn your guest in the help text if they'll be uploading large assets.

### Section 9 — How you heard about us *(Dropdown + conditional Single Line)*

**Custom HTML block:**

```html
<div style="margin:32px 0 12px 0;">
  <div style="font-family:'Space Grotesk',Arial,sans-serif;font-size:12px;letter-spacing:0.26em;text-transform:uppercase;color:#5D668B;">09 / Source</div>
  <h2 style="font-family:'Cormorant Garamond',Georgia,serif;font-size:36px;font-weight:500;color:#F3F4FA;margin:6px 0 6px 0;letter-spacing:-0.01em;">How you found iZZi</h2>
</div>
```

25. **How did you find us?** — *Custom Field → Dropdown → `lead_source`* — required. Options:
    - `Instagram`
    - `Referral from a past guest`
    - `Concierge service (Quintessentially, etc.)`
    - `Press / magazine`
    - `Google search`
    - `Podcast`
    - `Other`

26. **Who referred you?** — *Custom Field → Single Line → `referrer_name`* — conditional: show only if `lead_source` is `Referral from a past guest`. Placeholder `First + last name of your friend`.

### Section 10 — Consent & signature *(Checkbox × 2, Signature, Captcha)*

**Custom HTML block:**

```html
<div style="margin:32px 0 12px 0;">
  <div style="font-family:'Space Grotesk',Arial,sans-serif;font-size:12px;letter-spacing:0.26em;text-transform:uppercase;color:#5D668B;">10 / Consent</div>
  <h2 style="font-family:'Cormorant Garamond',Georgia,serif;font-size:36px;font-weight:500;color:#F3F4FA;margin:6px 0 6px 0;letter-spacing:-0.01em;">Before you send it</h2>
</div>
```

27. **SMS consent** — *Custom Field → Checkbox → `sms_consent`* — required. Label text (paste verbatim):

    > By checking this box, I consent to receive non-marketing text messages from iZZi Retreats about my retreat — including confirmation, itinerary updates, and day-of logistics. Message frequency varies. Message & data rates may apply. Text HELP for assistance, reply STOP to opt out.

28. **Privacy / Terms acknowledgement** — *Custom Field → Checkbox → `privacy_ack`* — required. Label HTML:

    ```html
    I have read and agree to the <a href="/privacy" style="color:#5EEAD4;text-decoration:underline;">Privacy Policy</a> and <a href="/terms" style="color:#5EEAD4;text-decoration:underline;">Terms of Service</a>.
    ```

29. **Guest signature** — *Custom Field → Signature → `guest_signature`* — required. Label: `Sign with your finger or mouse`.

30. **Captcha** — Drag the *Captcha* form element in. No configuration — it uses the account-wide reCAPTCHA.

31. **Source** — Drag a *hidden* Source input at the very top of the form (above Section 1) and set its value to `izzi-retreats-intake`. This lets you trace which page / campaign the submission came from in workflows.

> **Teaching note — Source field.** Every form submission records a *source* — by default it's the form name. Adding an explicit hidden Source element lets you override that with a cleaner slug and adds a field you can query inside workflows (`if source contains "intake"`).

32. **Submit button** — Click the submit element on the canvas and set the label to `Send my vision`. All visual styling (gradient, glow, radius) is handled in the Styling Guide via Custom CSS.

---

## Conditional logic

Configure under **Conditional Logic** in the form builder.

| Target field | Show when |
|---|---|
| `referrer_name` | `lead_source` is `Referral from a past guest` |
| `medical_form_file` | `retreat_type` is `Adventure & expedition` |
| `work_phone` | `retreat_type` is `Corporate offsite` |
| `companion_names` | `party_size` > `1` |

> **Teaching note — Conditional logic.** GHL evaluates conditions on every keystroke. Keep them flat — `A shows when B is X` — rather than nested (`A shows when B is X AND C is Y AND D is not empty`). Nested logic is technically possible but painful to maintain and debug.

---

## Tags on submission

Add under **Settings → Tags on submit** (always applied), plus conditional tags via workflow.

Always-applied:

- `izzi_intake_open`

Conditional (set via a workflow that listens to the form submission):

- `izzi_retreat_wellness` — when `retreat_type` is `Wellness & spa`
- `izzi_retreat_adventure` — when `retreat_type` is `Adventure & expedition`
- `izzi_retreat_creative` — when `retreat_type` is `Creative & writing`
- `izzi_retreat_silent` — when `retreat_type` is `Silent / meditation`
- `izzi_retreat_corporate` — when `retreat_type` is `Corporate offsite`
- `izzi_intensity_gentle` / `izzi_intensity_balanced` / `izzi_intensity_intensive` — keyed off `intensity_level`

Lifecycle tags (applied by downstream workflow):

- `izzi_intake_in_review`
- `izzi_intake_quoted`
- `izzi_intake_closed_won`
- `izzi_intake_closed_lost`

---

## Site embed

On the Lovable site `/plan-your-retreat` page:

```tsx
<!-- FORM_GOES_HERE: Experience Intake -->
<GhlFormEmbed
  src="https://api.leadconnectorhq.com/widget/form/YOUR_FORM_ID_HERE"
  title="iZZi Retreats Experience Intake"
  minHeight={2200}
/>
```

Iframe requirements inside the `GhlFormEmbed` component:

- `style={{ width: "100%", minHeight: "2200px", border: "none", background: "transparent" }}`
- `scrolling="no"`
- Include the GHL embed script once: `<script src="https://link.msgsndr.com/js/form_embed.js"></script>`

Get the `src` URL from GHL: open the saved form → **Integrate form → Embed** → copy the `src` attribute from the iframe snippet → paste into the `src` prop above.

---

## Test checklist after saving

1. **Preview the form** in the GHL builder and scroll top to bottom — every section heading shows, every field is visible.
2. **Section-by-section sanity check** — confirm field order matches this guide.
3. **Conditional logic:**
   - Pick `Referral from a past guest` → `referrer_name` appears. Change it → field disappears.
   - Pick `Adventure & expedition` → `medical_form_file` appears.
   - Pick `Corporate offsite` → `work_phone` appears.
   - Set `party_size` to `1` → `companion_names` hides. Set to `2+` → it appears.
4. **File Upload** — upload one test image to `inspiration_files`, upload a PDF to `medical_form_file`. Submission should accept both.
5. **Signature** — draw a signature, confirm the preview shows the strokes.
6. **Captcha** — verify the reCAPTCHA badge renders. Submitting without solving it (if challenged) should block the submission.
7. **Submit a real test entry** with an email you own. Confirm:
   - Contact appears in GHL with email, phone, first/last name, DOB, and full address populated.
   - All custom field values land on the contact record.
   - `izzi_intake_open` tag applied; the correct `izzi_retreat_*` tag applied.
   - Hidden `source` reads `izzi-retreats-intake` on the submission record.
8. **SMS consent screenshot** — take a screenshot of the consent checkbox with the carrier-compliant language visible. Save it for Toll Free Verification submission.
9. **Embed check** — paste the iframe URL into the `src` on `/plan-your-retreat` in the Lovable site and confirm the form renders on the dark background with no white seam.
