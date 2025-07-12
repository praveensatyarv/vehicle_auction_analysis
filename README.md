# Vehicle Auction Data Analysis

## Problem Statement
This project analyzes a dataset of vehicles auctioned through a company that is a global leader in online vehicle auctions. The dataset includes attributes such as lot number, assignment date, sale date, yard zip code, make, model, pre-loss value, repair estimate, damage types, severity of damage, run condition, title group, odometer readings, and sale price.

**Objective:** Uncover actionable insights and patterns in vehicle assignment and sales, aiming to reduce holding costs and improve sales velocity. The analysis seeks to answer:
* What factors contribute to longer assignment-to-sale durations?
* How do vehicle make, damage type, and severity impact turnaround time and sale price?
* What process improvements could expedite sales and optimize operations?

## Data Preprocessing

### 1. Initial Exploration:
* Loaded the vehicle auction dataset and performed exploratory data analysis.
* Checked for missing values and data types across key columns.

### 2. Data Cleaning:
* Removed duplicate rows to ensure analysis accuracy.
* Handled missing values:
   * For numerical columns (like Odometer, Pre-Loss Value, and Repair Estimate), missing values were imputed using median values.
   * For categorical columns (like Damage Type and Severity), missing values were filled with 'Unknown'.
* Converted date columns (Assignment Date, Sale Date) to datetime objects for time calculations.

### 3. Feature Engineering:
* Created a new column `Assignment_to_Sale_Days` by calculating the difference in days between Assignment Date and Sale Date.
* Categorized vehicles based on the duration of assignment periods (e.g., <15 days, 15-30 days, >30 days).
* Extracted additional features such as vehicle age and grouped damage types for further insights.

### 4. Data Transformation:
* Encoded categorical variables as needed for analysis.
* Filtered outliers (e.g., vehicles with extremely high assignment-to-sale periods or sale prices) to focus on typical auction flows.

## Final Observations & Conclusions

* **Assignment Delays:** Certain makes and damage types are associated with significantly longer assignment-to-sale periods, with some vehicles exceeding 40 days.
   * Vehicles with 'Severe' or 'Frame Damage' and certain brands (e.g., BMW, Mercedes) had notably longer turnaround times.
* **Holding Costs & Sales Velocity:** Delays in assignment directly contribute to increased holding costs and slower inventory turnover, impacting overall profitability.
* **Sale Price Drivers:** Sale price showed a moderate correlation with pre-loss value, odometer readings, and damage severity.
   * Well-maintained vehicles with lower damage severity fetched higher sale prices and sold faster.
* **Run Condition & Title:** Vehicles in 'Run & Drive' condition or with 'Clean Title' tended to have shorter assignment-to-sale durations and higher average sale prices.

## Suggestions

* **Targeted Process Improvements:** Implement cross-functional initiatives to fast-track processing and sales for vehicle makes and damage types prone to delays (e.g., streamline documentation or prioritize repair estimates).
* **Inventory Segmentation:** Segment inventory based on risk factors (make, damage type, severity) and develop tailored sales strategies (e.g., batch auctions, fast-track lanes for high-value/low-damage vehicles).
* **Monitoring & Early Intervention:** Deploy dashboards/alerts to monitor vehicles approaching high assignment-to-sale durations, enabling proactive intervention to reduce bottlenecks.
* **Data Enrichment:** Incorporate additional external data (e.g., market demand trends, regional buyer activity) to enhance predictive modeling and inventory optimization.