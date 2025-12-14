# rfm-customer-segmentation
Customer segmentation using RFM analysis

Project Overview

		This project performs customer segmentation using RFM (Recency, Frequency, Monetary) analysis on an online retail dataset.
		The objective is to understand customer purchasing behavior, identify high-value customers, detect churn risk, and support data-driven marketing strategies.
		
		The project follows an end-to-end data analytics workflow, using:
		
		SQL for data cleaning and aggregation
		
		Python for RFM scoring and segmentation
		
		Power BI for interactive dashboard visualization

Business Objectives

		Identify high-value customers (Champions & Loyal Customers)
		
		Detect at-risk and hibernating customers
		
		Understand revenue contribution by customer segments
		
		Enable targeted marketing and retention strategies

Tools & Technologies

		Database: MySQL 8
		
		SQL Tool: MySQL Workbench
		
		Programming Language: Python
		
		Libraries: Pandas, NumPy
		
		Notebook Environment: Google Colab
		
		Visualization: Power BI Desktop
		
		Dataset: Online Retail Dataset (UCI Machine Learning Repository)

Dataset Description

		The dataset contains transactional data from an online retail store, including:
		
		InvoiceNo
		
		InvoiceDate
		
		CustomerID
		
		Quantity
		
		UnitPrice
		
		Country
		
		After cleaning:
		
		~392,000 valid transactions
		
		4,338 unique customers

Data Cleaning (SQL)

		Data cleaning was performed in MySQL to ensure accurate RFM calculations:
		
		Removed cancelled invoices (InvoiceNo starting with C)
		
		Removed returns and invalid transactions (Quantity <= 0)
		
		Removed zero or negative prices
		
		Removed records with missing CustomerID
		
		Removed duplicate rows
		
		Ensured correct data types for dates and monetary values
		
		This step ensured only valid purchase behavior was analyzed.

RFM Metrics Calculation

		RFM metrics were calculated using SQL aggregation:
		
		Recency: Days since the customer’s last purchase
		
		Frequency: Number of distinct transactions per customer
		
		Monetary: Total spending per customer
		
		A reference date (2011-12-10) was used to calculate Recency.
		
		Result:
		A table with one row per customer containing Recency, Frequency, and Monetary values.

RFM Scoring (Python)

		Raw RFM values were converted into standardized scores from 1 to 5 using quintile-based scoring:
		
		R_Score: Lower recency → higher score
		
		F_Score: Higher frequency → higher score
		
		M_Score: Higher monetary value → higher score
		
		A combined 3-digit RFM score (e.g., 555, 421) was created for each customer.

Customer Segmentation

		Customers were grouped into meaningful segments based on RFM scores, including:
		
		Champions
		
		Loyal Customers
		
		Potential Loyalists
		
		Big Spenders
		
		At Risk
		
		Hibernating
		
		New Customers
		
		These segments help businesses design targeted retention, reactivation, and growth strategies.

Power BI Dashboard
		
		An interactive one-page Power BI dashboard was created to visualize insights:
		
		Dashboard Features:
		
		KPI cards (Total Customers, Revenue, Avg Recency, Avg Frequency)
		
		Customer segment distribution
		
		Revenue contribution by segment
		
		RFM heatmap (Recency vs Frequency)
		
		Top customers table
		
		The dashboard provides both executive-level overview and analytical depth.

Key Insights

		Champions and Loyal Customers generate the majority of revenue
		
		A significant number of customers fall into Hibernating and At-Risk segments
		
		High-frequency but low-recency customers indicate churn risk
		
		Targeted campaigns can significantly improve customer retention
