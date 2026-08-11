# Updating your site

Everything lives in one file: `index.html`.
Open it in any plain-text editor — Notepad on Windows, TextEdit on Mac
(Format → Make Plain Text first), or VS Code if you want colour coding.

Save, then re-upload. That's the whole workflow.

---

## Where things are

The file is split into commented sections. Search for these markers:

| Looking for | Search the file for |
|---|---|
| Name, job title, intro paragraph | `<div class="hero shell">` |
| Clearance / certification strip | `<div class="creds">` |
| "How I work" paragraphs | `id="about"` |
| The four focus boxes | `focus-grid` |
| Job history | `id="experience"` |
| Tools and methods table | `id="skills"` |
| Certifications and degree | `id="credentials"` |
| Email, phone, LinkedIn | `id="contact"` |

---

## Adding a new job

Copy an existing block from the Experience section and change the text.
Each one looks like this:

```html
<div class="job">
  <div class="when">Sep 2024 — Present<em>Washington, DC</em></div>
  <div>
    <h3>QA Automation Engineer</h3>
    <p class="org">U.S. Department of Agriculture</p>
    <ul>
      <li>First accomplishment.</li>
      <li>Second accomplishment.</li>
    </ul>
  </div>
</div>
```

- `when` — dates, then the location inside `<em>` tags
- `h3` — your job title
- `org` — the employer
- each `<li>` — one bullet

Paste the new block **above** the USDA one so it appears first, and change
the old top job's dates from "Present" to its end month.

Keep bullets to five or six per role. Start each with a verb and include a
number where you can.

## Adding a certification

In the Credentials section, copy one line:

```html
<li><strong>Certification name</strong><span>Issuing body · 2026</span></li>
```

## Turning on Recommendations

Search for `RECOMMENDATIONS`. The whole section is wrapped in a comment —
the `<!--` before it and the `-->` after it. Paste your quotes in, then
delete those two markers and the section appears.

## Changing the colour

Near the top, inside `:root`, is `--accent:#1F4E46;` — the dark green.
Change that one value and every button, link, and border follows.

---

## Re-publishing

**Netlify Drop** (easiest, free): go to https://app.netlify.com/drop and drag
in a folder containing:

```
index.html
RishatChowdhury.pdf
rishat-photo.jpg
```

To update later, drag the whole folder onto the Production deploys drop box
on your Netlify project page. Always the folder, never a single file — each
deploy replaces the entire site with whatever the folder contains.

If something breaks, open **Deploys** in the Netlify sidebar, pick the last
working version, and click Publish deploy. Every past version is kept.

**Custom domain:** already done. `rishatchowdhury.com` is registered at
Porkbun; DNS stays at Porkbun with an ALIAS on the root pointing to
`apex-loadbalancer.netlify.com` and a CNAME on `www` pointing to
`rishatchowdhury.netlify.app`. Don't change those.

---

## Before you publish, check

- Open the file in a browser and click every link
- Resize the window narrow to confirm it still reads on a phone
- Confirm the résumé button downloads the right PDF
- Search the file for `Lorem`, `TODO`, or `[` to catch leftovers
