# QuickBite Express — Crisis Recovery Insights Dashboard (Codebasics RPC #18)

## Power BI Dashboard
- **PBIX (download):** `dashboard/QuickBite.pbix` (GitHub won’t preview PBIX files in-browser)
- **PDF (preview):** https://lnkd.in/e8viBg5y

## Dashboard Preview:
<img width="1295" height="752" alt="Image" src="https://github.com/user-attachments/assets/bbceef93-6f7d-437c-be4d-9b54c4180e25" />

---

## Problem Statement

QuickBite Express is a Bengaluru-based food-tech startup (founded in 2020) that connects customers with nearby restaurants and cloud kitchens.

In **June 2025**, QuickBite faced a major crisis. A viral social media incident involving **food safety violations** at partner restaurants, combined with a **week-long delivery outage** during the monsoon season, triggered massive customer backlash. Competitors capitalized with aggressive campaigns, worsening the situation.

This project analyzes how the crisis impacted **orders, revenue, delivery performance, customer trust, and restaurant partnerships**, and builds a **Power BI recovery dashboard** to guide leadership decisions.

---

## What this dashboard shows

- Monthly and phase-wise **order & revenue trends** (Pre-crisis vs Crisis)
- **City-level decline** and cancellation hotspots
- Restaurant-level impact: **top declining restaurants**, cuisine & partner type performance
- Delivery operations: **SLA compliance**, average delivery time, delays & cancellations
- Customer trust signals: **ratings trend**, sentiment & negative keyword analysis (word cloud)
- Customer retention: **loyal customer churn**, high-value customer decline patterns

---

## Data Source

Datasets were provided as part of the **Codebasics Resume Project Challenge #18** and include transactional and dimensional tables for:

- Orders & order items
- Delivery performance
- Customer ratings & reviews (with sentiment)
- Customers, restaurants, delivery partners, menu items
- Supporting metadata documents

> Raw data was cleaned in Python and exported as clean CSVs for modeling in Power BI.

---
## Python notebooks

This repository includes the cleaned datasets used in the dashboard and the cleaning notebook so the project is reproducible.

Suggested structure:


---

## Steps Followed

### 1) Data Understanding & Cleaning (Python)
- Loaded all source tables and reviewed data quality (nulls, duplicates, datatypes)
- Standardized categorical fields (city, cuisine, partner type, acquisition channel)
- Converted timestamp columns into proper datetime formats
- Handled missing delivery partner IDs for cancelled orders using a consistent label
- Engineered key recovery features:
  - **Order phase**: Pre-crisis vs Crisis
  - **Delivery delay (mins)** and **delay buckets**
  - **SLA flag**: on-time vs delayed
  - Numeric estimate for restaurant prep time
- Created a **date dimension** spanning the min/max dates across all tables
- Exported clean files as `*_clean.csv`

Notebook:
- `notebooks/data understanding and cleaning.ipynb`

### 2) Data Modeling & Dashboarding (Power BI)
- Imported cleaned CSVs and built a star-schema style model (facts + dimensions)
- Created DAX measures for:
  - Orders, revenue, cancellations, delivery KPIs, ratings, churn/retention
  - Pre-crisis vs Crisis comparisons and % change
- Built a 5-page interactive dashboard with slicers and drilldowns

---

## Dashboard Pages

### 1) Crisis Overview
- Monthly order trend + phase-wise comparison
- Top cities by decline in orders
- High-level KPI comparison across phases

### 2) Restaurant Performance
- Top high-volume restaurants with the largest crisis decline
- Cuisine and partner type impact

### 3) Delivery Performance
- Avg delivery time change, delay distribution and SLA compliance
- Cancellation rate trend and city-wise cancellation comparison

### 4) Ratings & Sentiment + Revenue
- Month-by-month rating trend (sharp drop post June 2025)
- Negative review keywords (word cloud)
- Revenue mix comparison and revenue loss estimate

### 5) Customer Retention & Recovery
- Loyal customer churn (5+ pre-crisis orders)
- Loyal inactive customers with high ratings
- Top 5% high-value customer decline and common patterns (city, cuisine, delays)

---

## Key Insights

- 📦 Orders fell **114K → 35K (-69%)** during the crisis phase  
- 💰 Revenue dropped **₹37.6M → ₹10.9M (-71%)**  
- ⭐ Average rating declined **~4.5 → ~2.5**, reflecting major trust loss  
- ⏱️ Average delivery time increased **~39 min → ~60 min**  
- 🚫 Cancellations nearly doubled across major cities  
- 👥 **84% of loyal customers churned** (5+ pre-crisis orders)

---

## Recommended Recovery Strategies

- **Rebuild Trust (Food Safety)**
  - Audits, transparent compliance badges, and communication campaigns
- **Fix Delivery Operations**
  - SLA monitoring by city, monsoon contingency planning, supply balancing
- **Win-back Loyal & High-Value Customers**
  - Targeted offers + reassurance messaging based on city/cuisine behavior
- **Protect Key Restaurant Partnerships**
  - Prioritize high-performing, high-retention partners for long-term stability

---

## Tools Used

- **Power BI** (data modeling, DAX measures, slicers, dashboard design)
- **Python** (Pandas, NumPy) for cleaning and feature engineering

---

## Future Improvements

- Add a **Recovery Phase** tracking layer (post-Sep 2025) with cohort-based reactivation metrics
- Build a churn prediction model (Logistic/XGBoost) using order + delay + sentiment signals
- Add “restaurant risk score” combining cancellations, ratings, and SLA breaches
- Automate refresh using scheduled pipelines (Power BI Service + dataflow)

---

## Author

Created by **Ashish Dey**

Feel free to open an issue or connect for suggestions and improvements.



