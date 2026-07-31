# Ifeanyi — Product Portfolio

A lightweight product-management portfolio, hosted free on GitHub Pages. Plain HTML/CSS — no build step, no framework.

**Live site:** `https://<your-username>.github.io/` (once deployed — see below)

## What's inside

```
portfolio/
├── index.html                          ← Landing page (about, work grid, contact)
├── case-multicurrency-checkout.html    ← Case study 1: Afriex Collect multi-currency checkout
├── mockup.html                         ← Prototype 1 (embedded in case study 1)
├── case-send-to-china.html             ← Case study 2: CNAPS-guided transfers to China
├── send-to-china-mockup.html           ← Prototype 2 (embedded in case study 2)
├── case-wedding-gifting.html           ← Case study 3: cross-border group wedding gifting
├── wedding-gift-mockup.html            ← Prototype 3 (embedded in case study 3)
├── files/
│   ├── Afriex-Collect-Multicurrency-Checkout-PRD.docx   ← PRD 1
│   └── Afriex-Send-to-China-CNAPS-PRD.docx              ← PRD 2
├── data/                               ← Open reference data (China bank / CNAPS)
│   ├── china-banks-selected.csv        ← ~74k rows, major banks
│   ├── china-banks-other.csv           ← ~74.7k rows, other banks
│   ├── curated-banks.json              ← Subset powering prototype 2
│   └── DATA-DICTIONARY.md              ← Column definitions & notes
├── .nojekyll                           ← Tells GitHub Pages to serve files as-is
└── README.md
```

The `data/` folder publishes the bank/CNAPS reference data so anyone can inspect or reuse it — GitHub previews the CSVs and renders the data dictionary. See [`data/DATA-DICTIONARY.md`](data/DATA-DICTIONARY.md).

## Deploy to GitHub Pages (no command line needed)

1. **Create a repo.** On GitHub, click **New repository**. For a personal site at `https://<username>.github.io`, name it exactly `<username>.github.io`. (Any other name works too — the URL just becomes `https://<username>.github.io/<repo-name>/`.) Set it to **Public**.
2. **Upload the files.** On the empty repo page, click **uploading an existing file**. Drag in everything from this `portfolio/` folder — including the `files/` folder and the hidden `.nojekyll`. Commit.
3. **Turn on Pages.** Go to **Settings → Pages**. Under *Build and deployment*, set **Source: Deploy from a branch**, **Branch: `main`**, folder **`/ (root)`**. Save.
4. **Wait ~1 minute**, then refresh the Pages settings — your live URL appears at the top. Done.

## Before you publish — personalize

Search each file for `[EDIT]` and the yellow note banners, then update:

- Your **full name / headline / pitch** in `index.html`
- **Location**, and the **About** copy
- **Contact links** — email, GitHub, LinkedIn (currently placeholders)
- In the case study, tune **My role** and swap the illustrative **metrics** for real results once the feature ships

## Add another case study later

1. Copy an existing `case-*.html` file to a new file (e.g. `case-yourproject.html`).
2. Replace the content sections (problem, role, approach, solution, outcomes).
3. Add a matching `<a class="case">` card in the work grid in `index.html` (replace the "Coming soon" placeholder).

## A note on the large CSVs

The two China CSVs are ~9 MB each. That's fine for GitHub (the limit is 100 MB per file), and they'll download cleanly. GitHub renders a preview for smaller CSVs; for large ones it shows a "view raw / download" option — still fully accessible. If you'd rather keep the repo lean, you can drop the CSVs and keep just `curated-banks.json` + the data dictionary.

---

Built as a starting point — everything is editable plain HTML.
