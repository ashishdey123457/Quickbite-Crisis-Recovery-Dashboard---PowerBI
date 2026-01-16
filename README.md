# QuickBite Express — Crisis Recovery Insights Dashboard (Codebasics RPC #18)

### Dashboard Link:
(Add your Power BI public link here)

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

## Data Files

This repository includes the cleaned datasets used in the dashboard (and/or the cleaning notebook) so the project is reproducible.

Suggested structure:
