# E-commerce Sales Analysis

## Short description
Data analysis and insights from the E_commerce notebook and cleaned transaction dataset. The project explores category performance, order volumes, monthly trends, regional behavior, and provides measurable business recommendations.

## Repository description
E-commerce sales exploratory analysis (Jupyter notebook) with cleaning steps, visualizations, and actionable recommendations to reduce concentration risk and grow revenue.

---

## Project overview
This repository contains a Jupyter notebook (`E_commerce.ipynb`) and a cleaned CSV (`Cleaned_Ecommerce.csv`) that together analyze 100k+ e-commerce transactions. The analysis focuses on: category revenue vs order volume, monthly sales trends, region and segment comparisons, and recommendations that convert observations into measurable experiments.

Key goals:
- Quantify revenue and order volume by product category, region, and customer segment.
- Identify concentration risks and differences between category order volumes and revenue.
- Evaluate monthly/seasonal sales patterns and detect campaign effects.
- Propose actionable business recommendations and KPI targets.

---

## Files in this repository (top-level)
- E_commerce.ipynb — Jupyter notebook with the analysis and visualizations.
- Cleaned_Ecommerce.csv — cleaned dataset used by the notebook (100500 rows originally; 100019 after deduplication during cleaning).
- README.md — this file.

## Dataset (as used in the notebook)
- Rows: originally 100,500; after dropping duplicates the notebook reports 100,019 rows.
- Columns: Order_ID, Order_Date, Ship_Date, Customer_ID, Customer_Segment, Region, State, Product_Category, Sub_Category, Product_Name, Sales, Quantity, Discount, Profit, Shipping_Cost, Payment_Mode

Cleaning steps performed in the notebook:
- Filled missing Customer_Segment with mode.
- Filled missing Profit with the median profit.
- Filled missing Shipping_Cost with the median shipping cost.
- Removed duplicate rows.
- Converted Order_Date and Ship_Date to datetime and numeric conversion for Sales and Profit.
- Basic logical validation (e.g., checking Ship_Date vs Order_Date).

---

## Summary of methods
- Data loading and cleaning as listed above.
- Aggregations by Product_Category, month (Order_Date), Region, and Customer_Segment.
- Computation of Average Order Value (AOV) per category: revenue / number_of_orders.
- Visualizations: category revenue share, monthly revenue trend, orders vs revenue per category, and regional/segment comparisons.

---

## Key findings & insights
Electronics accounts for an estimated ~77% of total sales — a concentration risk. A single bad quarter for that category (supply issue, competitor pricing, demand shift) would sink overall revenue with no cushion from other categories. Recommendation: set a category-diversification target (e.g., grow Furniture/Clothing to a combined 35% of sales within two quarters) and track it as a KPI, not just a one-time observation.

Furniture and Clothing generate similar order volumes to Electronics but far less revenue. This points to a lower average order value or price point in those categories, not lower demand. Recommendation: test bundling or upselling within Furniture/Clothing orders to lift average order value without needing new customers.

Monthly sales are essentially flat — no seasonal or holiday spikes. For most retail categories this is unusual and suggests either untapped seasonal demand or an absence of timed campaigns. Recommendation: run one deliberate seasonal promotion (e.g., a defined holiday window) and compare lift against the flat baseline to test whether the flatness is a demand issue or a marketing gap.

Regions and customer segments perform almost identically to one another. Uniform performance usually means pricing and promotions aren't tailored locally. Recommendation: pilot one region-specific or segment-specific offer and measure whether it outperforms the uniform approach — if it does, that's your business case for regional strategy.

---

## Business recommendations (actionable & measurable)
1. Category diversification KPI
   - Target: grow Furniture + Clothing share to 35% of sales in 2 quarters.
   - Measurement: weekly category sales share; report to stakeholders.
   - Experiment: promote Furniture/Clothing with discounts or bundle offers and measure lift in revenue share.

2. Increase AOV in low-revenue categories
   - Hypothesis: bundling/upselling increases AOV for Furniture/Clothing without reducing order volume.
   - Experiment: A/B test 1 — show curated bundles vs control; metric = % change in AOV and revenue per user.

3. Test seasonality with a controlled promotion
   - Design: one defined holiday or seasonal window (e.g., 4-week campaign).
   - Metric: incremental revenue vs control period; uplift by segment and category.

4. Region / segment targeted offer pilot
   - Select one region/segment to pilot tailored pricing/promotion.
   - Metric: conversion or revenue uplift relative to the uniform baseline.

---

## How to run the notebook
1. Clone the repository:

   git clone https://github.com/Nandikondabharath/Data-Analytics-Projects-Python.git

2. Create and activate a virtual environment:

   python -m venv venv
   source venv/bin/activate  # macOS/Linux
   venv\Scripts\activate     # Windows

3. Install dependencies (example):

   pip install pandas numpy matplotlib seaborn jupyterlab

4. Open the notebook:

   jupyter lab
   - Open `E_commerce.ipynb` and run cells in order. The notebook reads the CSV from the local path used during analysis — update file path if needed (the notebook originally read `ecommerce_dirty_dataset.csv` locally).

---

## Suggested repository improvements
- Add a `requirements.txt` generated from the notebook imports.
- Export main charts to `figures/` for quick preview in the repository.
- Add a compact `results/summary.csv` with aggregated KPIs (category revenue share, order counts, AOV) for reviewers who don't want to run the full notebook.
- Replace any absolute local file paths in `E_commerce.ipynb` with relative `data/` paths and include `Cleaned_Ecommerce.csv` in `data/` or instructions to download it.

---

## Contact
Maintainer: Nandikondabharath

If you'd like, I can update the README further to include exact category revenue shares, AOV numbers, and PNGs of plots directly extracted from `E_commerce.ipynb`. Reply and I will add those and commit them to the repo.
