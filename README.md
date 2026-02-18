# Blinkit Retail Performance & Revenue Analytics Dashboard
End-to-end business intelligence case study analyzing retail revenue performance, outlet segmentation, product category contribution, and regional sales trends. Built an interactive Power BI dashboard to identify growth drivers, operational gaps, and data-driven expansion opportunities.

## Project Background

Blinkit is a quick-commerce grocery delivery platform operating across multiple outlet formats and city tiers. As competition intensifies in the online grocery space, leadership requires structured visibility into revenue performance, outlet efficiency, and product contribution.

This project transforms item-level retail sales data into a strategic, decision-ready business intelligence case study designed for non-technical stakeholders.

The primary objectives of this analysis are to:

- Identify key revenue drivers across product categories  
- Evaluate outlet performance by size and location tier  
- Assess sales distribution patterns across city segments  
- Highlight operational strengths and potential expansion opportunities  

The outcome is an executive-focused dashboard that converts raw transactional data into actionable commercial insights.
## Key Metrics Analyzed

To evaluate Blinkit’s retail performance and revenue composition, the following business-critical metrics were analyzed:

- **Total Sales ($)** – Overall revenue generated across outlets  
- **Average Sales per Item (AOV Equivalent)** – Revenue efficiency per unit sold  
- **Number of SKUs Sold** – Product volume and assortment breadth  
- **Average Product Rating** – Customer satisfaction proxy indicator  
- **Sales by Item Category** – Revenue contribution by product type  
- **Sales by Outlet Type** – Performance comparison across supermarket formats  
- **Sales by Outlet Size** – Revenue impact by store scale  
- **Sales by Location Tier (Tier 1, 2, Tier 3)** – Geographic revenue distribution  
- **Sales by Item Fat Content** – Product composition impact on revenue  
- **Outlet Establishment Year Performance** – Maturity-based revenue analysis  

These metrics collectively provide a structured view of revenue concentration, operational efficiency, and growth potential across Blinkit’s retail network.

## Executive Focus Areas

Based on the metrics analyzed, insights and strategic recommendations are structured around the following business themes:

1. **Sales Trend Analysis** – Revenue patterns across outlet establishment years  
2. **Product Performance** – Category-level revenue contribution and demand concentration  
3. **Regional Performance** – Revenue distribution across Tier 1, Tier 2, and Tier 3 markets  
4. **Outlet Performance** – Format and size-based revenue efficiency comparison  
5. **Operational Strategy Gaps** – Revenue concentration risks and expansion opportunities  

## Data Structure & Initial Validation

### Data Source
- **BlinkIT Grocery Data.xlsx**
- Item-level retail dataset
- Total records: 8,523

---

### Dataset Structure

The dataset is a single flat transactional table combining item-level attributes and outlet-level attributes.

**Key Fields Included:**

- `Item Fat Content` (Categorical)
- `Item Identifier` (Unique SKU ID)
- `Item Type` (Product Category)
- `Outlet Establishment Year` (Year Opened)
- `Outlet Identifier` (Store ID)
- `Outlet Location Type` (Tier 1 / Tier 2 / Tier 3)
- `Outlet Size` (Small / Medium / High)
- `Outlet Type` (Grocery Store / Supermarket Type1 / Type2 / Type3)
- `Item Visibility` (Numeric)
- `Item Weight` (Numeric)
- `Sales` (Revenue per record)
- `Rating` (Customer rating)

---

### Conceptual ERD (Production-Level Design)

For enterprise deployment, the dataset would ideally be normalized into:

- **Items Table**
  - item_id
  - item_type
  - fat_content
  - weight
  - visibility

- **Outlets Table**
  - outlet_id
  - outlet_type
  - outlet_size
  - location_tier
  - establishment_year

- **Sales Table**
  - sale_id
  - item_id
  - outlet_id
  - transaction_date
  - sales_amount
  - rating

Currently, the provided dataset represents a denormalized sales table containing both item and outlet attributes.

---

### Initial Data Validation Checks

Before conducting the analysis, the following validation steps were performed:

- Total Rows: **8,523**
- Total Revenue: **$1,201,681.49**
- Average Sales per Record: **$140.99**
- No missing values in critical revenue or segmentation fields
- Minor null values observed in `Item Weight` (non-impacting for revenue analysis)
- Category and outlet labels were standardized and suitable for aggregation

The dataset was deemed structurally sound for revenue and segmentation analysis.

## Executive Summary

The analysis reveals three primary revenue drivers within Blinkit’s retail network: outlet format efficiency, category concentration, and geographic segmentation.

**1. Sales Trend & Outlet Maturity**
Outlets established in 2018 generated a noticeable revenue peak compared to other establishment years. However, revenue levels have since stabilized rather than accelerating. This indicates that early expansion yielded strong returns, but incremental growth now requires operational optimization rather than footprint expansion alone.

**2. Product Performance Concentration**
Revenue is heavily concentrated within a small number of categories, primarily Fruits & Vegetables and Snack Foods. These categories form the core revenue engine of the business. Conversely, categories such as Breakfast and Seafood contribute minimal share, presenting controlled experimentation opportunities for assortment optimization.

**3. Regional & Outlet Performance**
Tier 3 locations generate the highest total revenue, outperforming Tier 1 and Tier 2 markets. Medium-sized outlets deliver the strongest revenue contribution relative to scale, while Supermarket Type1 formats dominate total sales share. This suggests that format standardization and targeted Tier 3 expansion could enhance overall performance.

Overall, the findings indicate that Blinkit’s growth strategy should shift from expansion-led momentum to format optimization, category prioritization, and geographic focus.

## Insights Deep Dive

Below are the six core visualizations from the Blinkit dashboard. For each chart I explain what the chart shows, why it matters for the business, and the concrete action to take. Read this section as a story: the data shows where Blinkit won early, where demand is concentrated today, and where to focus operational effort to restart growth.

---

### Figure 1 — Total Sales by Outlet Establishment Year  
![Total Sales by Outlet Establishment Year](assets/sales_by_est_year.png)

**What this shows**  
Outlets opened in 2018 contribute a clear revenue spike compared with other establishment years. After 2018, annual sales by establishment-year level off around the \$120–\$135k range.

**Why it matters**  
The 2018 cohort appears to have benefited from a reproducible set of factors (location, assortment, launch support). Subsequent openings did not replicate that uplift, so expansion alone is not currently delivering the same ROI.

**Action**  
Run a rapid “2018 cohort audit”: map those outlets against location attributes, top SKUs, and launch marketing assets. Codify the playbook and pilot it on 3 recent outlets. Measure lift by orders per outlet (target +15% in 90 days).

---

### Figure 2 — Average Sales (AOV Equivalent) by Outlet Establishment Year  
![Average Sales (AOV) by Outlet Establishment Year](assets/aov_by_est_year.png)

**What this shows**  
Average sales per record remain tightly clustered around \$140 with only modest variance across establishment years.

**Why it matters**  
The 2018 revenue spike is volume-driven (more orders or more outlets), not because customers spent more per order. That tells us to prioritize order-generation tactics rather than basket-size tactics to regain growth.

**Action**  
Prioritize volume experiments: targeted promotions, time-limited discounts, and local partnerships to increase order frequency. Track uplift in order count vs AOV to validate the hypothesis.

---

### Figure 3 — Top 10 Item Types by Total Sales  
![Top 10 Item Types by Total Sales](assets/top10_item_types.png)

**What this shows**  
Fruits & Vegetables and Snack Foods are the top two revenue categories. Household and Frozen Foods follow. Low-volume categories include Breakfast and Seafood.

**Why it matters**  
Revenue concentration in a few categories creates both strength (clear winning categories to protect) and risk (overreliance). High performers should receive priority for stock, placement, and promotion; underperformers warrant controlled experiments.

**Action**  
1. Protect the winners: increase shelf prominence and implement automated replenishment for core SKUs.  
2. Experiment with underperforming categories via 4-week promotional pilots with measured uplift thresholds (if conversion < baseline, reduce SKU depth).

---

### Figure 4 — Sales by Outlet Location Tier  
![Sales by Outlet Location Tier](assets/sales_by_tier.png)

**What this shows**  
Tier 3 locations produce the most total sales, then Tier 2 and Tier 1.

**Why it matters**  
This contradicts the common assumption that metro (Tier 1) markets always lead. Blinkit’s strongest pockets of demand are in emerging/secondary markets, which should shape expansion and assortment decisions.

**Action**  
Shift marketing and assortment investment toward top-performing Tier 3 segments. Build localized assortments that mirror Tier 3 top SKUs and run targeted acquisition campaigns (referral credits, first-order discounts) in select Tier 3 micro-markets.

---

### Figure 5 — Sales Share by Outlet Size  
![Sales Share by Outlet Size](assets/sales_by_size.png)

**What this shows**  
Medium outlets contribute the largest share (~42%), followed by small (~37%) and high/large (~21%).

**Why it matters**  
Medium format appears to be the operational sweet spot — it balances assortment breadth with manageable fulfillment costs. Large outlets are not automatically delivering proportionally higher sales.

**Action**  
Standardize the medium-outlet template (assortment plan, inventory buffer, staffing model) and prioritize medium-format conversion or replication for new openings. For existing large outlets, run a format optimization audit to determine whether scaling down or format changes improve throughput.

---

### Figure 6 — Sales by Item Fat Content  
![Sales by Item Fat Content](assets/sales_by_fat.png)

**What this shows**  
Low-fat products account for a substantially larger revenue share compared with regular-fat and mixed labels.

**Why it matters**  
There is a visible customer preference for healthier/low-fat offerings. This is an actionable positioning opportunity for Blinkit to differentiate on health-focused assortment and promotions.

**Action**  
Create a “Health Essentials” category in the app, promote private-label low-fat bundles, and test margin-improving private-label SKUs in this segment. Monitor uptake and AOV impact over the next quarter.

---

## Cross-cutting recommendations (prioritized)

1. **Codify and replicate the 2018 playbook** — high priority. Audit 2018 outlets, create a launch checklist, and run a pilot on 3 outlets.  
2. **Concentrate on Medium-format expansion and Tier 3 markets** — medium priority. Reallocate expansion and marketing budget toward these formats and tiers for higher ROI.  
3. **Protect top categories and test low-performers** — immediate. Ensure stock reliability for Fruits & Vegetables and Snack Foods while running small-scale promotional tests for Breakfast and Seafood.  
4. **Build customer-level instrumentation** — strategic. Add `customer_id`, `order_id`, and `transaction_date` to enable retention, cohort, and promotional lift analysis.  
5. **Operationalize alerts and KPIs** — tactical. Implement stockout alerts for top 50 SKUs and weekly dashboards for Orders-per-Outlet and AOV trend.

---

## How to present these insights to non-technical stakeholders

- Lead with the core story: *“We grew fast through expansion; now growth requires optimization.”*  
- Use two slides: (1) Executive summary with the three primary findings and recommended next step; (2) Evidence slide with the six visuals and 1-line takeaway under each.  
- Anchor recommendations to impact: e.g., “Apply 2018 playbook — expected +10–20% orders in pilot outlets.”

---

## Next analysis steps (data and experiments)

- **Instrument customer-level data** (customer_id, order timestamp) to measure retention and AOV lift.  
- **Add refund/return fields** to track net revenue and product quality issues.  
- **Run uplift tests** for promotions (randomized controlled trials in matched outlets).  
- **Drill into SKU-level performance** across outlet tiers to build localized assortments.

---

### Short caveat
This analysis is based on the provided, denormalized sales snapshot. Lack of transaction dates and customer identifiers limits cohort and retention analysis; the recommended instrumentation fixes will unlock richer, higher-confidence insights.

