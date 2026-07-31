# Ifeanyi — Product Portfolio

A lightweight product-management portfolio, hosted free on GitHub Pages. Plain HTML/CSS — no build step, no framework.

**Live site:** `https://<your-username>.github.io/` (once deployed — see below)

## What's inside

```
portfolio/
├── index.html                         ← Landing page (about, work grid, contact)
├── case-multicurrency-checkout.html   ← Case study: Afriex Collect multi-currency checkout
├── mockup.html                        ← Interactive prototype (embedded in the case study)
├── files/
│   └── Afriex-Collect-Multicurrency-Checkout-PRD.docx   ← Downloadable PRD
├── .nojekyll                          ← Tells GitHub Pages to serve files as-is
└── README.md
```

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

1. Copy `case-multicurrency-checkout.html` to a new file (e.g. `case-yourproject.html`).
2. Replace the content sections (problem, role, approach, solution, outcomes).
3. Add a matching `<a class="case">` card in the work grid in `index.html` (replace the "Coming soon" placeholder).

---

Built as a starting point — everything is editable plain HTML.
