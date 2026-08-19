# NovaCard Physician Adoption Dashboard

A pharma commercial-analytics project that segments physicians, identifies what actually drives prescribing, and turns both into a prioritized commercial action plan.

**[View the live dashboard →](https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/)**
*(replace with your GitHub Pages URL once enabled — see setup below)*

---

## The problem

A new heart-and-metabolism drug ("NovaCard") was being prescribed by only **10.3%** of doctors, despite heavy investment in making it available. The goal: figure out which physicians to focus limited sales and access resources on to grow prescriptions fastest.

## The core insight

The biggest group of doctors isn't skipping the drug because they don't know about it — **it's because the drug is too costly or hard to get for their patients.** That reframes the whole plan: fix the cost/coverage problem for the biggest group, and prioritize outreach to a smaller group that's already ready to prescribe but under-visited.

## Approach

- **Segmentation** — K-Means clustering grouped 800 physicians by six behaviors (rep visits, digital engagement, peer influence, competitor loyalty, patient cost, drug coverage), then each cluster was given a plain-English name.
- **Driver analysis** — Logistic regression and Random Forest models (0.81 / 0.75 accuracy) were trained to identify what separates prescribers from non-prescribers, cross-checked against each other.
- **Prioritization** — Segments were plotted on market size vs. current adoption to make the resourcing trade-off explicit.

## Key findings

| Segment | Doctors | Adoption Rate | Eligible Patients | Profile |
|---|---|---|---|---|
| Advocates | 176 | 17.0% | 32,625 | Reps visit often, easy coverage — already converting |
| White Space | 203 | 16.3% | 36,268 | Easy coverage, strong peer influence, but reps rarely visit |
| Access-Constrained | 421 | 5.9% | 77,399 | ~Half the market; hardest formulary tier, highest patient cost |

**Top drivers of prescribing:** peer influence (+), competitor loyalty (–), and cost-sensitive/Medicare patient mix (–). Adoption drops from 18.8% (easy coverage) to 4.2% (restricted coverage) — proof the biggest segment's problem is access, not awareness.

## Recommendation

1. **Focus on White Space first** — best return on the next commercial dollar
2. **Fix Access-Constrained's coverage problem** before spending more rep time there
3. **Maintain Advocates** with light-touch effort
4. **Screen out high competitor-loyalty physicians** from the first push

## Repository contents

```
├── index.html                    # Interactive dashboard (Overview / Segments / Priority tabs)
├── NovaCard_Case_Study.docx      # Full written case study
├── tableau_physician_data.csv    # Physician-level dataset (800 rows)
└── driver_importance.csv         # Model feature-importance scores
```

## Tech stack

Python (pandas, scikit-learn) for clustering and modeling · Chart.js for the interactive dashboard · HTML/CSS/JS, no build step required.

## Data note

Built on a synthetic 800-physician dataset designed to mirror realistic pharma prescribing patterns (rep visits, peer influence, cost sensitivity, formulary access). Not real patient or prescriber data.

## Setup / hosting this yourself

1. Clone or fork this repo
2. Rename the dashboard file to `index.html` (already done if you're using this repo as-is)
3. In **Settings → Pages**, set source to `main` branch, root folder
4. Your live dashboard will be at `https://<your-username>.github.io/<repo-name>/`
