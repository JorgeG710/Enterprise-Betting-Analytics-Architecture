> **Security & Compliance Note:** The dataset within this repository has been sanitized. User IDs have been cryptographically hashed and financial metrics have been scaled by a constant factor to ensure strict NDA compliance. Core mathematical relationships, win/loss ratios, and behavioral patterns remain fully intact for accurate architectural demonstration.

## 📌 The Business Problem
* **Context:** A high-volume international gaming platform was experiencing misaligned reporting between transactional stake data and unique user behavior, hindering accurate commercial strategy.
* **Objective:** Architect an end-to-end data pipeline to deduplicate records, standardize multi-region data, and build a scalable delivery model for tracking Gross Gaming Revenue (GGR), Average Revenue Per User (ARPU), and predictive churn.

## 🏗️ The Medallion Architecture (Data Engineering)
* **Bronze Layer (Ingestion):** Ingested **842,000+ raw transactional rows**. Identified and purged 1,437 duplicate transaction IDs that were artificially inflating the company's revenue metrics.
* **Silver Layer (Transformation):** Utilized Python (Pandas) to standardize 18 distinct regional currencies (including SGD, IDR, THB) into a single base currency. Enforced strict data typing and handled null timestamp logic for live vs. pre-match indicators.
* **Gold Layer (Business Logic):** Built declarative dimensional models. Materialized complex behavioral flags (e.g., identifying "Cross-Sport Switchers") upstream in the Python pipeline rather than relying on heavy DAX filter contexts, ensuring the final BI engine remained lightweight and highly performant.

## 📊 Commercial Delivery & Strategic Insights (Data Analytics)
* **Hold vs. ARPU Quadrant:** Segmented regional brands into a 2x2 matrix, allowing executive stakeholders to easily identify high-value/low-volume platforms versus low-value/high-volume platforms.
* **Behavioral Migration (Churn Reframing):** Proved through overlapping set analysis that 957 users did not "churn" out of the ecosystem entirely, but successfully migrated from Basketball to Football betting, drastically altering the retention strategy.
* **Predictive Outlook:** Modeled a projected 7-14% drop in active accounts based on upcoming seasonal sporting calendars, allowing the business to proactively adjust marketing spend.

## 🛠️ Tech Stack & Methodology
* **Pipeline Engineering:** Python (Pandas), SQL
* **Delivery & Visualization:** Power BI, Advanced DAX, PowerPoint
* **Architecture:** Kimball Dimensional Modeling, Medallion Architecture (Bronze/Silver/Gold)

---
*For a detailed look at the delivery layer and strategic recommendations, please refer to the presentation deck located in the `/dashboards` folder.*
