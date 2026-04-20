# 🏨 Hospitality Revenue & Booking Intelligence Dashboard (Power BI)

## 🎯 Executive Summary
**GrandStay Hotels** required a centralised intelligence dashboard to optimise operations and enhance the guest experience. This project transforms raw booking and guest data into actionable insights, providing visibility into revenue generation, demographic trends, and booking source profitability.

## 🛠️ Technical Stack & Data Modelling
*   **Tool:** Power BI Desktop
*   **Data Structure:** Relational Model (1-to-Many Star Schema) linking `Guests` and `Bookings` tables.
*   **Calculations:** Custom **DAX Measures** developed for core business KPIs.

## 📈 Key Business Solutions Delivered

### 1. Executive Booking Insights (DAX Integration)
Engineered custom DAX measures to provide an instant operational snapshot:
*   **Total Revenue Generated:** Calculated overall business profitability.
*   **Completed Bookings:** Tracked the exact volume of successful stays.
*   **Average Duration (Days):** Analysed guest retention and stay patterns for completed bookings.

### 2. Operational Trend Analysis
*   **Monthly Booking Trends:** Visualised seasonality across all booking statuses to support staffing and resource allocation during peak periods.
*   **Room Type Popularity:** Displayed the proportion of bookings by room type (Standard, Deluxe, Suite) to identify guest preferences and prioritise high-demand offerings.

### 3. Revenue & Demographic Optimisation
*   **Source Analysis:** Analysed the distribution of bookings across acquisition channels (Website, Travel Agents, Walk-ins) to inform targeted marketing ROI.
*   **Profitability by Source:** Identified the most profitable booking sources segmented by Room Type, allowing management to optimise third-party partnerships.
*   **Demographic Revenue:** Visualised revenue proportion by age category, highlighting the core customer segments driving profitability.

### 4. Interactive Data Exploration
*   **Detailed Booking Ledger:** Developed a granular table containing full guest itineraries, room types, and generated revenue.
*   **Dynamic Filtering:** Implemented cross-filtering slicers (Booking Date, Booking Source, Booking Status) to allow stakeholders to drill down and conduct tailored analysis in real-time.

---
*This project was completed as part of the Professional Certificate in Data Analytics & AI (Code Institute).*

## 📸 Dashboard Visualisation & Architecture

### 1. Executive Revenue Overview
This view showcases the high-level KPIs, providing an instant summary of the £147K total revenue and demographic segmentation.
![Main Dashboard](Dashboard_main.png)

### 2. Dynamic Data Exploration
By utilising interactive slicers (e.g., filtering for 'Website' bookings), the dashboard dynamically updates all visuals, allowing for granular performance analysis.
![Filtered Dashboard](dashboard_filtered.png)

### 3. Relational Data Model (ERD)
The backend architecture utilises a 1-to-Many relationship between the 'Guests' and 'Bookings' tables to ensure data integrity and efficient DAX calculations.
![Data Model](data_model.png)

### 🧠 DAX Logic & Analytical Measures
To drive the business logic of the dashboard, I developed custom DAX measures. Below are key examples of the analytical engine used:

**1. Total Revenue Generation**
Calculates the aggregate revenue across all completed bookings.
```dax
Total Revenue Generated = SUM(Bookings[Revenue Generated])
```
**2. Completed Booking Volume**
A dynamic count that filters out cancellations.
code
```daxDax
Completed bookings = CALCULATE(COUNTROWS(Bookings),Bookings[Booking Status] = "Completed")
```
**3. Average Stay Duration**
Provides insight into guest behavior by calculating the mean length of stay for completed transactions.
```dax
Avg Duration Days = 
AVERAGEX(
    FILTER('Bookings', 'Bookings'[Booking Status] = "Completed"),
    DATEDIFF('Bookings'[Check-in Date], 'Bookings'[Check-out Date], DAY)
)
```
