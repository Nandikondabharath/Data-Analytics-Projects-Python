# E-commerce Sales Analysis

This project analyzes a cleaned e-commerce sales dataset to surface business insights and recommended actions for category, regional, and campaign strategy.

Dataset
- File: Cleaned_Ecommerce.csv
- Rows: 100,500 (original), cleaned version used in analysis in this repo
- Key columns: Order_ID, Order_Date, Ship_Date, Customer_ID, Customer_Segment, Region, State, Product_Category, Sub_Category, Product_Name, Sales, Quantity, Discount, Profit, Shipping_Cost, Payment_Mode

Executive summary

- Electronics accounts for an estimated ~77% of total sales — a concentration risk. A single bad quarter for that category (supply issue, competitor pricing, demand shift) would sink overall revenue with no cushion from other categories. Recommendation: set a category-diversification target (e.g., grow Furniture/Clothing to a combined 35% of sales within two quarters) and track it as a KPI, not just a one-time observation.

- Furniture and Clothing generate similar order volumes to Electronics but far less revenue. This points to a lower average order value or price point in those categories, not lower demand. Recommendation: test bundling or upselling within Furniture/Clothing orders to lift average order value without needing new customers.

- Monthly sales are essentially flat — no seasonal or holiday spikes. For most retail categories this is unusual and suggests either untapped seasonal demand or an absence of timed campaigns. Recommendation: run one deliberate seasonal promotion (e.g., a defined holiday window) and compare lift against the flat baseline to test whether the flatness is a demand issue or a marketing gap.

- Regions and customer segments perform almost identically to one another. Uniform performance usually means pricing and promotions aren't tailored locally. Recommendation: pilot one region-specific or segment-specific offer and measure whether it outperforms the uniform approach — if it does, that's your business case for regional strategy.

What I added
- This README with the business insights and recommended next steps.
- A small Python utility (scripts/compute_metrics.py) that computes the numeric KPIs you asked for from Cleaned_Ecommerce.csv and writes results to results/category_metrics.csv and results/summary.md.

Next step (run locally)
1. Run the script to compute exact numbers and produce a short markdown summary that can be pasted into this README.

Commands

```bash
# from the repo root
python3 scripts/compute_metrics.py --input Cleaned_Ecommerce.csv --outdir results
```

Outputs
- results/category_metrics.csv — Category-level metrics: Category, Orders, Revenue, Revenue%, AOV
- results/summary.md — Small markdown snippet with total revenue, total orders, and a short monthly trend line that you can paste here in the README

If you want, I can also: generate and commit the computed results into the README automatically if you provide permission to run a CI job with a repo write token, or if you run the script locally and paste the generated results here I will update the README with the exact numbers.

Notes
- The analysis text above is based on the dataset and the insights you provided. The compute script will calculate exact numeric values and save both CSV and a short markdown summary.

License / Contact
- Author: @Nandikondabharath
