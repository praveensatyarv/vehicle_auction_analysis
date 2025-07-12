# Vehicle Auction Data Analysis

## Problem Statement
The goal of this project is to analyze a dataset containing information on vehicles auctioned through a company that is a global leader in online vehicle auctions. The data includes a variety of attributes related to each vehicle, such as its lot number, assignment date, and sale date, yard zip code, make and model, pre-loss value, repair estimate, damage types, severity of damage, run condition, title group, odometer readings, and sale price.

The objective of this analysis is to uncover insights and patterns within the data that could help improve the company's auction efficiency and sales performance. This includes identifying relationships between various attributes and the final sale price of the vehicles, understanding how different factors such as damage severity and repair estimates affect sale prices, and exploring how the timing of events (e.g., assignment date and sale date) impacts the sale process.

Through this analysis, potential solutions and strategies can be proposed to optimize the company's operations and enhance sales outcomes. This includes identifying areas for improvement in inventory management, auction timing, vehicle preparation, and more. By examining the data in depth, the project aims to provide actionable insights to support Copart's ongoing success in the vehicle auction market.

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

* Lot of make like GMC, MERCEDES, and BMW take the longest to be assigned to the company. But they also go for high prices in auction. The company can work with the insurance companies to expediate the asssignment of these specific lots. Same goes for vandalised lots.

* As the difference between the lot assignment date and the lot invoice date increases, the auction price of the lot increases. This could imply that a longer time between assignment and invoicing may be associated with higher prices. The reasons for this relationship could be multifaceted: Market Timing, Time for Vehicle Prep, and Better Quality Checks.

* Understanding which lots take longer to auction can help to manage salvage yards better. For example, lot make like KIA, DODGE, CHEVROLET, JEEP, and HYUNDAI are the slowest to auction. Whereas lot make TOYOTA, PONTIAC, SATURN, SUZUKI, and MERCEDES are the quickest to auction.
 
* Yards have an effect on the lot sale price (max <- min): 
                Yard (zip-85043) > Yard (zip-87105) > Yard (zip-85706)
The reasons for this difference could be: Local Marker Conditions (Vehicle Distribution) and Yard Specific Practices.

* Lots make plays a vital role in determining its auction price. Certain makes, such as COLE, SPNR, and TEX, are associated with higher auction prices, while other makes, such as INTL, KZ, and MG, are associated with lower auction prices. These differences could be due to a variety of factors: Brand Reputation, Vehicle quality, and Demand for specific makes. Understanding these relationships can help make more informed decisions regarding vehicle valuation and auction strategies.

* Serious primary damages such as VP (replaced VIN) and VI (missing/altered VIN) take the longest time (40 days) to get assigned to the company from the insurance companies. After being assigned, it takes around 40 days for the lot to get auctioned, which is almost the same as for other lot damages.


## Suggestions

* Given the positive correlation between assignment to invoice cycle time and auction price, increasing the cycle time could result in higher auction prices. Optimize the processing and preparation time by enhancing vehicle inspections, repairs, and quality control checks. This can improve the overall condition of the vehicles and thus command higher auction prices. Analyze historical data to identify optimal time frames for processing vehicles and adjust operational practices accordingly.
* Invest in or improve operations at yards with fewer lots auctioned (such as the ones in zip codes 87105 and 85706) to leverage untapped potential and boost overall sales.
* Focus on promoting high-performing makes (COLE, SPNR, TEX) in marketing and sales strategies to attract buyers and increase the auction prices of the vehicles.
* Consider special handling procedures for vehicles with vandalism damage types to expedite the assignment and auction processes, ensuring they are not delayed unnecessarily.
* Continuously monitor and analyze market trends, buyer preferences, and pricing strategies in different regions and for different makes and damage types. Use this data to refine auction strategies and set competitive prices that reflect current market dynamics.