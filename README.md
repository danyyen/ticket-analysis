# ticket-analysis
You have been asked to produce a summary on trends and patterns in Ticket count between 2015 and 2025, inclusive. While the basis of this analysis is expected to be derived from the ferry tickets dataset available on the Open Data Catalogue (Toronto Island Ferry Ticket Counts - City of Toronto Open Data Portal ... https://open.toronto.ca/catalogue/), you are encouraged to integrate this dataset with other publicly available sources of data or information. The City is looking to improve the Ferry service ahead of a busy summer season. As a first step, they are seeking to understand the trends and patterns that exist in ticket sales over the last ten (10) years.

# To analyze ferry ticket sales over the past ten years, I adopted a structured, data science-driven approach:

1.	Data Cleaning & Integration:
o	Loaded 15 minutes’ interval data of Ferry ticket sales. Aggregated to daily interval for better trend and seasonality analysis. 
o	Web scraped daily weather data of ‘Toronto Ontario City’  from https://climate.weather.gc.ca/
o	Merged daily ferry ticket datasets (sales and redemptions) with daily weather records using a left join.
o	Handled non-numeric anomalies (e.g., "LegendMM", "LegendEE") and imputed missing values where necessary using surrounding averages. Checked for duplicates, outliers, inconsistencies and data-types.
2.	Exploratory Data Analysis (EDA):
o	Conducted trend analysis by day, month, and season to uncover usage spikes.
o	Visualized ticket activity against weather factors (mean temperature, precipitation).
o	Used heatmaps and correlation plots to assess relationships among key variables.
3.	Feature Engineering:
o	Introduced flags for weekends, holidays, and season changes.
o	Calculated rolling averages to smooth short-term volatility.
4.	Visualization for Insights:
o	Created seasonal line charts, calendar heatmaps, and Prophet forecast plot with labeled axes, legends, and confidence bands to support storytelling.
5.	Time Series Modeling:
o	Performed decomposition to isolate trend, seasonality, and residuals.
o	Built forecasting model:
	Prophet (because it takes note of seasonality): included holiday effects like Canada Day, Civic Holidays, and Christmas. Achieved R² = 0.73, RMSE = 2178, and MAE = 1539, indicating solid predictive performance.

# Assumptions Made
•	Historical sales patterns are consistent and predictive of future behavior.
•	Holidays have a significant effect on demand — particularly Canada Day and long weekends.
•	Weather impacts ferry demand linearly (e.g., warmer days’ correlate with higher sales).
•	Operational changes (e.g., fare increases or schedule changes) are not explicitly available and thus not modeled.
•	Covid-19 lockdown created a significant anomaly in sales and redemption count in year 2020-2021
•	There was also decline in ticket sales in 2017 possibly due to internal restructuring.
•	Assumptions were made for seasons. There could be some overlaps in due to climate change

# Next Steps (with More Data)
I would recommend:
1.	Customer Segmentation
o	Incorporate ticket types (adult, senior, group, etc.) or payment methods to tailor insights for different rider groups.
2.	Fleet Capacity and size data
o	Include ferry capacity, delays, local events, or service changes to distinguish between demand-side and supply-side impacts for better fleet allocation and cost reduction while meeting demands. 
3.	Advanced Forecasting Enhancements
o	Fine tune models or try SARIMA or other advanced models for better forecast. 
o	demands. 
4.	Dashboard Monitoring
o	Incorporate BI dashboards/reports to monitor Fleet Demands, Fleet in use/repair/break down/maintenance. Also incorporate total sales, demand, weather, precipitation and so on for optimal fleet service delivery.
