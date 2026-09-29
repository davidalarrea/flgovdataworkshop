# Florida Government Data Workshop — Genie Hands-on

Hands-on materials for the Databricks **Genie** portion of the Florida Government Data
Analytics & Intelligence Workshop — **Northwest Regional Data Center (NWRDC) × Databricks**,
Tallahassee, **October 6, 2026**.

You'll build your first Genie space on realistic Florida government data and learn the core
lesson first-hand: **context is the product.** Start with raw tables, watch Genie guess — then
add table/column descriptions, instructions, and metric views, and watch the same questions land.

## ✅ Before you start

You'll need access to a Databricks workspace. If you don't already have one, follow the
**[Free Edition setup guide](free-edition-setup.html)** to create a free, no-cost account and log
in before the session.

> Like the participant guide, this is an `.html` file — read it rendered via GitHub Pages
> (`https://davidalarrea.github.io/flgovdataworkshop/free-edition-setup.html`) or this
> no-setup preview: **[view rendered](https://htmlpreview.github.io/?https://github.com/davidalarrea/flgovdataworkshop/blob/main/free-edition-setup.html)**.

## 📘 Participant guide

**[Open the participant guide →](participant-guide.html)**

Full walkthrough: how to load the data, which questions to ask, and the exact context
(descriptions, instructions, and metric views) that makes the failing ones work.

> GitHub shows `.html` as source. To read it rendered, enable **GitHub Pages**
> (Settings → Pages → Branch: `main` / root) and open
> `https://davidalarrea.github.io/flgovdataworkshop/participant-guide.html`, or use this
> no-setup preview: **[view rendered](https://htmlpreview.github.io/?https://github.com/davidalarrea/flgovdataworkshop/blob/main/participant-guide.html)**.

## 🚀 Load a dataset (pick one)

Each notebook is **self-contained** — the data is bundled inside it, so there's nothing to
download or upload and **no cluster internet access is required**. Install only the one you want.

| Dataset | Notebook | Raw URL (for Import → URL) |
|---|---|---|
| **Spending** — contracts, payments, vendors | [`load_spending.py`](load_spending.py) | `https://raw.githubusercontent.com/davidalarrea/flgovdataworkshop/refs/heads/main/load_spending.py` |
| **Health** — county births/deaths, population, facilities | [`load_health.py`](load_health.py) | `https://raw.githubusercontent.com/davidalarrea/flgovdataworkshop/refs/heads/main/load_health.py` |
| **FDOT / Transportation** — projects, funding, change orders | [`load_transportation.py`](load_transportation.py) | `https://raw.githubusercontent.com/davidalarrea/flgovdataworkshop/refs/heads/main/load_transportation.py` |

**Steps (about a minute):**

1. In Databricks, click **Workspace** in the left sidebar.
2. **⋮ / Import → Import**, then either paste the notebook's **raw URL** above, or upload the `.py` **file**.
3. Open the notebook and attach it to any cluster or SQL warehouse.
4. Click **Run all** (▶▶). It creates the catalog `fl_gov_demo`, a schema, and three tables, then prints the row counts.

No rights to create a catalog? Change `CATALOG` in the notebook's second cell to one you can
already write to, then Run all again.

## 🧞 Build a Genie space

Point a new Genie space at the three tables in your schema (`fl_gov_demo.spending`,
`fl_gov_demo.health`, or `fl_gov_demo.transportation`) and start asking the questions from the
[participant guide](participant-guide.html).

> **Metric views** (used in the Health and FDOT sections) require a SQL warehouse or cluster on
> **Databricks Runtime 17.3+**.

## 📂 What's in this repo

| File | What it is |
|---|---|
| `free-edition-setup.html` | How to create a free Databricks workspace before the session |
| `load_spending.py` · `load_health.py` · `load_transportation.py` | Self-contained dataset loaders (import one, Run All) |
| `participant-guide.html` | The full participant walkthrough (load → build → ask → add context → dashboards) |

---

*Datasets are illustrative mock data modeled on real systems (FACTS/FLAIR, FLHealthCHARTS,
FDOT Work Program), not exact replicas. Prepared by Databricks Field Engineering for NWRDC.*
