# Tableau Hands-On Practice | Superstore Sales & Profitability

![Tableau](https://img.shields.io/badge/Tableau-Hands--on%20Practice-E97627?logo=tableau&logoColor=white)
![Dataset](https://img.shields.io/badge/Dataset-Sample%20Superstore-2563EB)
![Focus](https://img.shields.io/badge/Focus-Business%20Intelligence%20%26%20Data%20Visualization-475569)

A practical learning exercise exploring **retail sales, profit, geographic performance, and cumulative revenue** in Tableau. The goal was to learn Tableau by building real worksheets and an interactive dashboard—not to present a copied example as an original client project.

**Tools:** Tableau Public/Desktop · Calculated Fields · Table Calculations · Geographic Maps · Dashboard Filters

## Business questions

- Which product categories generate the most sales and the most profit?
- Why can a high-revenue category have a low profit margin?
- How does each category contribute to total revenue?
- Which US states are profitable or loss-making?
- How does cumulative sales revenue change over time?

## What I built

| Analysis | Tableau technique | Workbook |
| --- | --- | --- |
| Sales by Category | Horizontal bar chart, aggregation and sorting | [Main packaged workbook](./Superstore_Tableau_Practice.twbx) |
| Profit by Category | Comparison of category profitability | [Main packaged workbook](./Superstore_Tableau_Practice.twbx) |
| Profit Margin by Category | Calculated field, percentage formatting | [Main packaged workbook](./Superstore_Tableau_Practice.twbx) |
| Profit by State | Filled geographic map colored by profit | [Main packaged workbook](./Superstore_Tableau_Practice.twbx) |
| Sales Contribution % | **Percent of Total** table calculation | [Sales Contribution workbook](./Sales%20Contribution.twbx) |
| Cumulative Sales | **Running Total** table calculation with a line chart | [Cumulative Sales workbook](./Cumulative%20Sales.twbx) |
| Sales & Profit Dashboard | Combined views and dashboard filters | [Main packaged workbook](./Superstore_Tableau_Practice.twbx) |

The main workbook contains the combined Tableau practice; the two other packaged workbooks preserve individual calculation exercises.

## Results at a glance

Results shown here use the full Sample Superstore dataset (without region, year or category restrictions).

| Metric | Result |
| --- | ---: |
| Total sales | **$2,297,201** |
| Total profit | **$286,397** |
| Overall profit margin | **12.5%** |
| Highest sales and profit category | **Technology** |
| Lowest-margin category | **Furniture** |

### Category comparison

| Category | Sales | Profit | Profit margin | Share of sales |
| --- | ---: | ---: | ---: | ---: |
| Technology | $836,154 | $145,455 | 17.4% | 36.4% |
| Furniture | $742,000 | $18,451 | 2.5% | 32.3% |
| Office Supplies | $719,047 | $122,491 | 17.0% | 31.3% |

**Interpretation:** Furniture accounts for nearly a third of revenue yet contributes relatively little profit. Revenue alone is not a sufficient measure of business performance. The dashboard highlights where a deeper investigation of product mix, costs and discounting would be valuable; it does **not** establish causal effects.

## Screenshots and interactivity

- **Screenshots:** Visual previews can be added under `assets/` (for example, `dashboard.png`, `cumulative-sales.png`, and `sales-contribution.png`).
- **Workbook interaction:** Open the packaged Tableau workbook and use the Region, Category, Year and other available filters to explore results.
- **Browser interaction:** A public, clickable dashboard requires publishing the workbook to **[Tableau Public](https://public.tableau.com/)**. A live URL can be added here after publication. GitHub image previews are static.

## How to open the workbooks

1. Install [Tableau Public](https://www.tableau.com/products/public) or use Tableau Desktop.
2. Download `Superstore_Tableau_Practice.twbx` from this repository.
3. Open the `.twbx` file in Tableau. A packaged workbook includes the data and supporting files needed by the workbook.
4. Explore the worksheets and dashboard. Open the two separate `.twbx` files for the table-calculation exercises.

To **rebuild from the CSV** rather than opening the finished workbook, connect to `data/superstore.csv` once that file has been added to this repository. Verify date, numeric and geographic field roles after importing.

### Core calculated fields

**Profit Margin %** — aggregated profit divided by aggregated sales:

```tableau
SUM([Profit]) / SUM([Sales])
```

**Cumulative Sales** — computed along the year axis:

```tableau
RUNNING_SUM(SUM([Sales]))
```

**Sales Contribution %** — computed across categories:

```tableau
SUM([Sales]) / TOTAL(SUM([Sales]))
```

For the last two calculations, set the correct **Compute Using** direction in Tableau; a table calculation can return misleading values if its addressing/partitioning is incorrect.

## Dataset and attribution

- **Dataset:** Sample Superstore (US retail orders; 9,994 line items, 2015–2018 in this version).
- **Practice reference:** [ANAPBORGES/tableau-sales-profitability-dashboard](https://github.com/ANAPBORGES/tableau-sales-profitability-dashboard), which includes a copy of the sample CSV, design references and Tableau calculations.
- **Credit:** Original repository by Ana Paula Borges. This repository documents my own hands-on learning and adaptations, and is not presented as an independent original case study.

If redistributing the CSV, retain its source attribution and confirm that its distribution terms permit republication. If unsure, keep a download link to the source instead of committing a copy.

---

**Purpose:** Foundational Tableau practice in business reporting and visualization. For additional work, see my [GitHub profile](https://github.com/htoor2026).
