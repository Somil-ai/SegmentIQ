# SegmentIQ — Customer Segmentation & Sales Analytics

A fully client-side customer segmentation and sales analytics platform. No backend, no framework, no build tools — just a single HTML file you can open in any browser.

## Live Demo

Open `SegmentIQ — Customer Segmentation & Sales Analytics.html` directly in your browser. No installation needed.

## Features

- **RFM Segmentation** — Automatically segments customers into 6 groups based on Recency, Frequency, and Monetary scores
- **K-Means Clustering** — Unsupervised ML clustering (built from scratch) with configurable k (3–6)
- **Custom Segments** — Build your own segments using spend, order count, recency, age, and region filters
- **Churn Risk Scoring** — Every customer gets a High / Medium / Low churn risk label
- **Cohort Retention** — Monthly cohort retention table (M+0 to M+7) with trend chart
- **Insights & Recommendations** — Per-segment marketing strategies and product recommendations with lift analysis
- **Product Analytics** — Product performance table and stacked category revenue by segment
- **Customer Profiles** — Searchable customer table with full purchase history modal
- **Data Upload** — Import your own CSV or Excel file with auto column mapping and data cleaning
- **Export** — Download segmented data as CSV, Excel, or PDF
- **Dark / Light Theme** — Auto-detects system preference, manually toggleable

## Pages

| Page | Description |
|------|-------------|
| Dashboard | KPIs, charts, RFM heatmap, age distribution, churn risk |
| Segments | RFM table, custom segment builder, segment comparison, K-Means |
| Insights | Marketing strategies + product recommendations per segment |
| Products | Product performance, category revenue by segment |
| Customers | Searchable table with churn risk, clickable profile modal |
| Cohort Retention | Monthly cohort table + M+1 vs M+3 retention trend |
| Data & Cleaning | Upload CSV/Excel, column mapping, dedup, export |
| Methodology | RFM explanation, segment rules, K-Means, churn scoring |

## How to Use

### With Sample Data
Just open the HTML file — it loads 420 sample customers with realistic order history automatically.

### With Your Own Data
1. Go to **Data & Cleaning** page
2. Upload a CSV or Excel file (one row per order)
3. Map columns: Customer ID, Order Date, Amount (required) + Category, Product, Region (optional)
4. Click **Clean & Import**

Your CSV should look like this:

```
customer_id, name, date, amount, category, product, region
C001, John Smith, 2024-01-15, 199.00, Electronics, Smart Watch, North
C001, John Smith, 2024-03-22, 89.00, Electronics, Wireless Earbuds, North
C002, Jane Doe, 2024-02-10, 120.00, Fashion, Denim Jacket, South
```

## RFM Methodology

Each customer is scored 1–5 on three dimensions:

| Dimension | Description |
|-----------|-------------|
| **R — Recency** | Days since last purchase. Score 5 = bought very recently |
| **F — Frequency** | Total number of orders. Score 5 = most frequent buyer |
| **M — Monetary** | Total spend. Score 5 = highest spender |

### Segment Rules

| Segment | Rule | Description |
|---------|------|-------------|
| Champions | R≥4 & F≥4 | Best customers — recent, frequent, high spend |
| Loyal Customers | R≥3 & F≥3 | Regular buyers with good recency |
| New / Promising | R≥4 & F≤2 | Recent first or second-time buyers |
| Win-Back (High Value) | R≤2 & (F≥3 or M≥4) | Were valuable, now lapsing |
| Hibernating | R≤2 | Haven't bought in a long time |
| Needs Attention | All others | Mid-tier customers needing nurturing |

## Churn Risk Score

Churn risk = `(5 - R) × 2 + (5 - F) + (5 - M)`

- **High** — score ≥ 10
- **Medium** — score 6–9
- **Low** — score < 6

Recency is weighted 2× as it is the strongest predictor of churn.

## Tech Stack

| Technology | Purpose |
|------------|---------|
| Vanilla JavaScript (ES2022) | All logic, analytics, UI |
| Chart.js 4.4 | All charts and visualisations |
| SheetJS (xlsx 0.18) | CSV and Excel import/export |
| Google Fonts (Inter) | Typography |
| HTML5 + CSS3 | Structure and styling |

No frameworks. No backend. No build tools. No npm. Single file.

## Project Structure

```
SegmentIQ/
└── SegmentIQ — Customer Segmentation & Sales Analytics.html
└── README.md
```

## Screenshots

> Open the HTML file in your browser to see the live dashboard.

## License

MIT License — free to use, modify, and distribute.
