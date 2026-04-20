# 🏨 Hospitality Revenue & Booking Intelligence Dashboard (Power BI)

## 🎯 Executive Summary
**GrandStay Hotels** required a centralized intelligence dashboard to optimize operations and enhance the guest experience. This project transforms raw booking and guest data into actionable insights, providing visibility into revenue generation, demographic trends, and booking source profitability.

## 🛠️ Technical Stack & Data Modeling
*   **Tool:** Power BI Desktop
*   **Data Structure:** Relational Model (1-to-Many) linking `Guests` and `Bookings` tables.
*   **Calculations:** Custom **DAX Measures** developed for core KPIs.

## 📈 Key Business Solutions Delivered

### 1. Executive Booking Insights (DAX Integration)
Engineered custom DAX measures to provide an instant operational snapshot:
*   **Total Revenue Generated:** Calculated overall business profitability.
*   **Completed Bookings:** Tracked the exact volume of successful stays.
*   **Average Duration (Days):** Analyzed guest retention and stay patterns for completed bookings.

### 2. Operational Trend Analysis
*   **Monthly Booking Trends:** Visualized seasonality across all booking statuses to support staffing and resource allocation during peak periods.
*   **Room Type Popularity:** Displayed the proportion of bookings by room type (Standard, Deluxe, Suite) to identify high-demand offerings and prioritize inventory.

### 3. Revenue & Demographic Optimization
*   **Source Analysis:** Analyzed the distribution of bookings across acquisition channels (Website, Travel Agents, Walk-ins) to inform targeted marketing ROI.
*   **Profitability by Source:** Identified the most profitable booking sources segmented by Room Type, allowing management to optimize third-party partnerships.
*   **Demographic Revenue:** Visualized revenue proportion by age category, highlighting the core customer segments driving profitability.

### 4. Interactive Data Exploration
*   **Detailed Booking Ledger:** Developed a granular table containing full guest itineraries, room types, and generated revenue.
*   **Dynamic Filtering:** Implemented cross-filtering slicers (Booking Date, Booking Source, Booking Status) to allow stakeholders to drill down and conduct tailored analysis in real-time.

---
*This project was completed as part of the Professional Certificate in Data Analytics & AI (Code Institute).*

## 📸 Dashboard Visualisation & Architecture

### 1. Executive View (Default)
This view provides the high-level KPIs, including the £147K total revenue and overall demographic splits.
![Main Dashboard](Dashboard_main.png)

### 2. Interactive Filtering (Booking Source: Website)
The dashboard is fully interactive. In this view, the data is sliced to show only bookings originating from the 'Website', dynamically updating the revenue and room type visuals.
![Filtered Dashboard](dashboard_filtered.png)

### 3. Relational Data Model (1-to-Many)
The foundation of the dashboard. The `Guests` and `Bookings` tables are connected via a 1-to-Many relationship, ensuring data integrity and accurate DAX calculations.
![Data Model](data_model.png)
