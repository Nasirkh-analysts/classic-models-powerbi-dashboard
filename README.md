**Classic Models Sales Performance Dashboard**

**By Nasir Khan**

A 9-page Power BI dashboard analyzing sales, profitability, sales team performance, order/payment health, and customer opportunity for Classic Models, a global wholesale distributor of scale-model vehicles.

**Tools:** Power BI Techniques: Star/snowflake schema modeling, Calendar table, PATH/PATHITEM (organizational hierarchy), DAX measures (CALCULATE, time intelligence, ranking), Power Query data cleaning Data source: Classic Models MySQL sample database (Kaggle mirror), parsed into 8 relational tables

**Executive Summary**

Revenue peaked in 2004 and hasn't grown from new customers since — existing accounts now drive 68.84% of revenue, a demand-generation gap behind otherwise-healthy numbers.

The sales org carries concentration risk: Mami Nishi alone generates 4.76% of total revenue while informally managing Tokyo with no Sales Manager above her — a single point of failure.

Collections are a bigger issue than they first appear: $750K+ unpaid is actively blocking fulfillment, since every "On Hold" order traces back to an exceeded credit limit. EMEA carries the largest exposure ($377K), led by Euro+ Shopping Channel — a high-volume customer paying reliably, not a risk, despite the size of their balance.

There's also real untapped opportunity: the top 10 customers by credit limit use just 10.10% of it on average, room to sell more into accounts that already pay reliably.

**Bottom line:** the business isn't shrinking, but it is quietly fragile — dependent on one legacy customer base, one under-supported top performer, and a collections process that's now actively costing new sales.

**Dashboard Pages**
Executive Summary — Revenue trend, margin by product line, order fulfillment breakdown, engagement vs. credit utilization, revenue share by territory

Growth & Trend Analysis — Revenue from new vs. existing customers over time, seasonal demand patterns

Product Profitability — Top profit drivers, lowest contributors, volume vs. margin trade-offs

Sales Team & Regional Performance — Rep performance, revenue share by office and territory

Org Hierarchy Detail — 4-level reporting hierarchy (President → VP → Sales Manager → Rep) built with PATH/PATHITEM, headcount by territory

Order & Payment Health — Fulfillment and shipping breakdowns by region, cancellation and dispute rates

Order Comments Detail — Root-cause analysis of stuck orders and recurring product complaints

Customer Opportunity — Engagement ratio and credit utilization analysis to surface upsell potential

Data Cleaning — Documented data quality decisions and modeling choices

**Key Findings by Page**
Growth & Trend Analysis:
Revenue peaked in 2004; customer acquisition stopped entirely after that year.
Existing customers: 68.84% of revenue. New customers: 31.16%.
December consistently drives the highest monthly revenue.

Product Profitability:
Motorcycles post the best margin in the catalog (41.8%) despite smaller revenue than Classic Cars — the most profit-efficient line to scale.
Trains are weakest on both revenue and margin (~35%).
Individual standouts: 1992 Ferrari 360 Spider, 1952 Alpine Renault 1300, and 2001 Ferrari Enzo each generate $90K+ profit.

Org Hierarchy Detail:
Gerard Hernandez leads all reps with $1,258,577.81 in revenue.
Tom King and Yoshimi Kato show $0 in recorded revenue.
Japan is understaffed at the management level: 2 reps, no dedicated Sales Manager — Mami Nishi informally covers the gap.

Order & Payment Health:
APAC has the highest order cancellation rate of any region (5.26%).
EMEA carries the largest unpaid balance ($377,217.48); Japan collects 100% of what it bills but has the slowest shipping (6.25% late-ship rate).

Customer Opportunity:
Top 10 customers by credit limit use just 10.10% of it on average — headroom to sell more into low-risk accounts.
A handful of customers (Sharp Gifts Warehouse, Tekni Collectables, Gift 4 All Ages) exceed 100% credit utilization, signaling real collections risk rather than opportunity.

**Data Modeling Notes**
Built a snowflake schema across 8 tables with a dedicated Calendar table for time intelligence.
Used PATH and PATHITEM DAX functions to construct a 4-level sales hierarchy (President → VP → Sales Manager → Rep), since a standard table relationship can't traverse a "manager's manager's manager" chain.
Preserved intentional blanks during cleaning (e.g., the President's blank "reports to" field, missing ship dates on cancelled/in-progress orders) rather than filling them, since each blank carried real business meaning.
Correctly interpreted "NA" in the region field as North America, not a missing value — a common data-cleaning trap in this dataset.

**How to Use**
Open Classic_model_project.pbix in Power BI Desktop to explore the live model, DAX measures, and interactive visuals.
Or view Classic_Models_Dashboard.pdf for a static export of all 9 pages — no Power BI installation required.

