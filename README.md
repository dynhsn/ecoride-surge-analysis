# EcoRide: Surge Pricing & Customer Satisfaction Analysis

**Author:** Dayyan Hasan  
**Date:** August 2026  
**Tools Used:** Python, NumPy, Pandas, Matplotlib, Seaborn  

## Project Overview
EcoRide, a rapidly growing ride-sharing startup, has been experiencing a mysterious and severe drop in customer ratings. The executive team suspected that surge pricing might be the cause, but lacked the data to prove it. 

The objective of this exploratory data analysis (EDA) project was to clean a raw dataset of 1,000,000 ride logs, engineer missing financial metrics, and identify exactly what is causing the drop in customer satisfaction.

## Skills & Techniques Demonstrated
* **Data Wrangling (Pandas):** Handled missing data via median imputation (to preserve 450 valid ride records) and applied complex boolean filtering to remove corrupted zone data.
* **Vectorized Math (NumPy):** Calculated total ride fares across 1,000,000 rows instantly using NumPy array multiplication, bypassing slow Python `for` loops.
* **Data Aggregation:** Utilized the Split-Apply-Combine methodology (`.groupby().agg()`) to evaluate performance metrics across different operational cities.
* **Data Visualization (Seaborn/Matplotlib):** Designed clean, presentation-ready scatter plots to communicate complex correlation trends to non-technical stakeholders.

## Key Findings & Business Recommendation

After cleaning the data and visualizing the relationship between the `surge_multiplier` and `driver_rating`, a distinct behavioral trend was uncovered:

1. **Zone 1 (Business as Usual):** From 1.0x up to 2.5x surge pricing, there is **zero correlation** between price and ratings. Customers accept this as standard market fluctuation.
2. **Zone 2 (The Crisis Cliff):** The moment surge pricing crosses the **2.5x threshold**, a strong negative correlation begins. It becomes statistically impossible for a driver to achieve a 5-star rating, and ratings plummet toward 1 star.

**Recommendation to the CEO:** High surge pricing does not cause bad driving; it causes angry customers who unfairly punish drivers. EcoRide should implement a hard cap on the surge algorithm at **2.49x**. While this may slightly reduce short-term gross revenue, it will stop the hemorrhaging of customer goodwill and driver retention.

## Visual Proof
*(The chart below highlights the 2.5x "Crisis Cliff" where customer ratings collapse.)*

![EcoRide Surge vs Ratings](EcoRide_Crisis_scatterplot.png)

---

## How to Run This Project
1. Clone this repository to your local machine.
2. Ensure you have Python installed along with the required libraries: `pip install pandas numpy matplotlib seaborn`
3. Run the `ecoride_analysis.py` (or `.ipynb`) file to generate the clean dataset and view the visualizations.
