# GDS — AI Lab Governance & Deployment Score

A backward-looking, quarterly composite metric tracking governance quality across the four leading AI laboratories: **OpenAI, Anthropic, Google DeepMind, and Meta AI**.

## Formula

```
GDS = (PUCC_norm × 0.30) + (TAI_norm × 0.30) + (ES_norm × 0.40)
```

| Sub-score | Full name | Weight |
|-----------|-----------|--------|
| PUCC | Prohibited Use Category Count | 30% |
| TAI  | Transparency Artifact Index   | 30% |
| ES   | Enforcement Signal            | 40% |

## Deploying to GitHub Pages

1. Create a new GitHub repository (e.g. `gds-tracker`)
2. Drop `index.html` into the repo root
3. Go to **Settings → Pages → Source → Deploy from branch → main / root**
4. Your site will be live at `https://yourusername.github.io/gds-tracker`

## Updating Scores

All data lives in the `DATA` object inside `index.html` (around line 280). Each lab has three arrays — `pucc`, `tai`, `es` — one value per quarter. Add a new value to each array and a new label to `QUARTERS` each quarter.

```js
const QUARTERS = ['Q2 2024', ..., 'Q2 2026']; // add new quarter here

const DATA = {
  openai: {
    pucc: [11, 11, 12, ..., NEW_VALUE],
    tai:  [ 5,  5,  5, ..., NEW_VALUE],
    es:   [ 3,  3,  4, ..., NEW_VALUE],
  },
  // repeat for anthropic, google, meta
};
```

## Methodology

Full scoring rationale is documented in the **Methodology** tab of the site and in `GDS_Measurement_Framework.docx`.

Data coverage: **Q2 2024 → Q1 2026** (8 quarters). Updated quarterly.
