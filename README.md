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

# Insights Deep Dive

## 1. The 2018 Expansion Spike Discovery

<img src="Images/sales_by_est_year.png" width="700">

When analyzing revenue by outlet establishment year, the expectation was steady incremental growth as new outlets were added. Instead, the data revealed a concentrated performance spike.

- **2018 outlets show the highest total sales contribution**
- Post-2018 establishment years stabilize within a narrow revenue band
- Earlier years do not replicate the 2018 uplift

This suggests that growth in 2018 was not random. It likely resulted from a combination of favorable expansion strategy, outlet placement, assortment optimization, or launch execution.

### What This Reveals

The business experienced a moment of high expansion efficiency, but subsequent openings did not replicate that performance curve.

### Strategic Implication

Growth through expansion alone is no longer sufficient. Blinkit must shift from expansion-driven growth to performance optimization per outlet.

### Recommended Action

- Conduct a structured 2018 cohort audit (location, SKU mix, launch campaigns)
- Identify repeatable success factors
- Pilot a “2018 playbook” replication in 3–5 recent outlets
- Measure lift via order volume rather than revenue alone


---

## 2. The Volume vs Basket Size Discovery

<img src="Images/aov_by_est_year.png" width="700">

Average sales per record remain tightly clustered around ~$140 across establishment years.

- No meaningful AOV spike in 2018
- Revenue spike driven by order volume or outlet count
- Basket size stability across years

The 2018 uplift was volume-driven, not pricing-driven.

### Why This Matters

If basket size is stable, increasing AOV is unlikely to unlock material growth in the short term. Volume expansion is the true lever.

### Strategic Implication

Blinkit should prioritize order frequency and customer acquisition over basket expansion campaigns.

### Recommended Action

- Test flash promotions to drive order count
- Launch localized discount experiments in underperforming outlets
- Track Orders per Outlet as a core KPI
- Measure incremental volume lift before scaling campaigns


---

## 3. The Category Concentration Discovery

<img src="Images/top10_item_types.png" width="700">

Revenue is not evenly distributed across product categories.

- **Fruits & Vegetables and Snack Foods dominate total sales**
- Household and Frozen Foods follow as strong contributors
- Breakfast and Seafood show comparatively lower impact

### Three Structural Patterns Emerge

**Core Essentials Dominance**  
Daily-use items drive the revenue base.

**Impulse Category Strength**  
Snack Foods perform strongly, indicating high-margin impulse behavior.

**Long-Tail Underperformance**  
Certain categories consume shelf space without delivering proportional revenue.

### Strategic Implication

Not all categories deserve equal inventory investment or promotional focus.

### Recommended Action

- Protect top-performing categories with zero stockout tolerance
- Introduce dynamic shelf prioritization for high-frequency SKUs
- Run controlled experiments on underperforming categories
- Evaluate SKU rationalization for persistently low-volume items


---

## 4. The Tier 3 Market Leadership Discovery

<img src="Images/sales_by_tier.png" width="700">

Contrary to traditional retail assumptions:

- **Tier 3 outlets generate the highest total sales**
- Tier 2 follows
- Tier 1 contributes the lowest share among tiers

### Why This Matters

Secondary markets appear to offer stronger revenue efficiency relative to competition density.

### Strategic Implication

Future expansion and marketing investment should prioritize high-performing Tier 3 clusters.

### Recommended Action

- Accelerate medium-format openings in Tier 3 locations
- Localize assortment for Tier 3 consumption patterns
- Increase acquisition campaigns in high-performing Tier 3 zones
- Track Tier-level ROI before metro expansion


---

## 5. The Medium Outlet Sweet Spot Discovery

<img src="Images/sales_by_size.png" width="700">

Sales share by outlet size reveals:

- **Medium outlets contribute the largest share (~42%)**
- Small outlets follow (~37%)
- Large outlets underperform relative to footprint (~21%)

This challenges the assumption that bigger footprints automatically drive higher revenue.

### Why This Matters

Medium outlets likely balance operational efficiency, assortment breadth, and manageable cost structure.

### Strategic Implication

Blinkit’s most scalable format appears to be medium-sized outlets.

### Recommended Action

- Standardize the medium-format model as the primary expansion template
- Audit large outlets for operational inefficiencies
- Consider format optimization in large stores
- Monitor revenue per outlet and operational efficiency metrics


---

## 6. The Health Preference Signal Discovery

<img src="Images/sales_by_fat.png" width="700">

Sales by item fat content show:

- Low-fat items significantly outperform regular-fat items
- Health-oriented products contribute disproportionately to total sales

### Why This Matters

Consumer preference trends create margin and positioning opportunities.

Health-focused SKUs allow:
- Premium positioning
- Private-label differentiation
- Targeted marketing campaigns

### Strategic Implication

Blinkit can strengthen its positioning as a health-forward quick-commerce platform.

### Recommended Action

- Create a “Health Essentials” category within the app
- Launch private-label low-fat bundles
- Promote healthy impulse combinations
- Track margin contribution by health category


---

# Cross-Project Synthesis: Strategic Takeaways

This analysis reveals three structural realities about Blinkit’s business model:

1. Growth is no longer purely expansion-driven  
2. Revenue is concentrated in specific categories and outlet formats  
3. Secondary markets and medium outlets provide the strongest efficiency  

The next growth phase should focus on:

- Operational optimization over expansion  
- Category prioritization  
- Format standardization  
- Tier 3 scaling  
- Health-driven assortment positioning  

This marks the transition from early expansion to operational maturity.

# KPIs & Recommendations

Based on the insights and findings above, we would recommend Blinkit’s Operations and Growth Strategy teams focus on the following high-impact initiatives to transition from expansion-led growth to performance-driven optimization.

---

## 1. Standardize the Medium-Format + Tier 3 Expansion Model

The analysis reveals that medium-sized outlets contribute the highest share of total revenue (~42%), while Tier 3 markets outperform Tier 1 and Tier 2 locations in aggregate sales. This combination represents Blinkit’s most efficient growth engine.

Rather than expanding footprint indiscriminately, the strategy should prioritize replicating the medium-format model within high-performing Tier 3 regions. This ensures capital allocation aligns with proven revenue efficiency rather than assumed metro dominance. By codifying the operational model of successful medium-format stores and scaling it selectively, Blinkit can improve ROI per new outlet opening.

---

## 2. Protect and Scale Core Revenue Categories

Revenue concentration is heavily driven by Fruits & Vegetables and Snack Foods, which function as structural revenue anchors for the platform. These categories are not merely contributors; they are stability drivers for the entire sales ecosystem.

The recommendation is to implement zero-stockout tolerance policies for top SKUs within these categories, enhance in-app promotional visibility, and introduce dynamic replenishment forecasting. Protecting high-frequency, high-impact segments ensures revenue stability while other growth experiments are tested in parallel.

---

## 3. Transition from Expansion-Led Growth to Order-Volume Optimization

The 2018 outlet cohort generated a noticeable revenue spike; however, average sales per record remain stable across establishment years. This indicates that historical uplift was driven by order volume rather than increased basket size.

Future strategy should therefore prioritize increasing Orders per Outlet rather than focusing solely on pricing or basket expansion initiatives. By shifting attention to demand generation — localized promotions, acquisition campaigns, and outlet-level optimization — Blinkit can increase per-outlet productivity without relying purely on network expansion.

---

## 4. Implement Controlled Category Experimentation

Underperforming categories such as Breakfast and Seafood represent experimentation opportunities rather than immediate expansion candidates. Instead of increasing SKU depth reactively, Blinkit should implement structured A/B promotional pilots and scale only those categories demonstrating measurable incremental lift.

This disciplined testing framework ensures capital and shelf allocation decisions remain data-driven rather than intuition-based.

---

## 5. Instrument Customer-Level and Operational Data for Long-Term Growth

The current dataset does not include customer identifiers, transaction timestamps, or refund indicators. Without these fields, retention, repeat purchase behavior, and net revenue leakage cannot be measured.

Blinkit should enhance its data infrastructure by introducing customer_id, order_id, and return flags within the transaction schema. This enables cohort analysis, retention measurement, operational monitoring, and more advanced performance optimization over time.

---

# Key Performance Indicators

To operationalize the above strategy, the following KPIs should be continuously monitored:

---

## 1. Orders per Outlet

Total Orders / Active Outlets

Purpose: Measure outlet-level demand efficiency and validate performance-led growth strategy.

Target: Achieve 10–15% increase in Orders per Outlet in pilot markets within 90 days of optimization rollout.

---

## 2. Category Revenue Concentration Ratio

Top 3 Categories Revenue / Total Revenue × 100

Purpose: Monitor dependency risk on dominant categories while ensuring core segments remain protected.

Target: Maintain strength in core categories while improving secondary category contribution through controlled experimentation.

---

## 3. Tier-Level Revenue Efficiency

Total Sales per Tier / Number of Outlets in Tier

Purpose: Evaluate ROI of geographic expansion strategy.

Target: Sustain Tier 3 revenue leadership while improving Tier 1 productivity through localized assortment adjustments.

---

## 4. Stockout Rate for Top 20 SKUs *(Future KPI)*

Stockout Events / Total Availability Window × 100

Purpose: Protect structural revenue drivers and minimize lost sales.

Target: Maintain stockout rate below 3% for high-frequency SKUs.

---

## 5. Repeat Purchase Rate *(Requires Instrumentation)*

Returning Customers / Total Customers × 100

Purpose: Measure transition from acquisition-driven growth to retention-led revenue stability.

Target: Establish baseline after data instrumentation and achieve quarterly retention growth.

# Assumptions & Limitations

This analysis is based on a flat, cross-sectional retail sales dataset. While outlet establishment year is available, transaction-level timestamps are not included. As a result, granular time-series trend analysis could not be performed.

Customer identifiers and loyalty markers are absent from the dataset, limiting the ability to conduct retention, repeat purchase, or cohort-based analysis. Future data instrumentation should include customer-level tracking to unlock these insights.

The dataset does not contain refund, return, discount, or margin fields. Therefore, all revenue figures are assumed to represent gross sales. Inclusion of refund and promotion data would allow more precise net revenue and profitability modeling.

Sales values are assumed to be recorded in USD and reflect final transaction values without tax or shipping normalization adjustments.

Minor category-label variations (e.g., fat content classifications) were treated as recorded. Additional standardization may improve segmentation precision in future iterations.

# Next Steps

To evolve this case study into a production-grade analytics framework, the following steps are recommended:

- Introduce transaction_date, customer_id, refund_flag, and promotion_id into the sales schema.
- Deploy weekly KPI dashboards with alert thresholds for demand volatility.
- Run structured marketing pilots in underperforming categories and measure incremental lift.
- Develop a normalized data model (items, outlets, transactions) to support scalable analytics.
