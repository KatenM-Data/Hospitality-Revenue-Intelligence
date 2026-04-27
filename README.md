# 🏨 Hospitality Revenue Intelligence Dashboard (Power BI)

![Main Dashboard](Dashboard_main.png)

## 🎯 The Goal & Business ROI
GrandStay Hotels possessed 147,000+ unoptimised booking records, resulting in severe "data blind spots" regarding demographic profitability and commission leakage. 

*   **The Objective:** Build an automated, central "Source of Truth" to protect operating margins.
*   **The ROI:** Identified a 37% reliance on high-commission travel agents, providing a data-backed roadmap to reclaim **£15k+ annually** in lost margins.

---

## 💡 Strategic Insights & Recommendations
*Summary: Moving the business from Reactive Reporting to Proactive Intelligence.*

<details>
<summary><b>▶ Click to expand: Full Business Case & Solutions</b></summary>

### A. 💰 Protect Margins (Direct Booking Strategy)
**The Data:** 37% of bookings come through high-commission Travel Agents, vs. only 29% via the website.
*   **Solution:** Launch a "Book Direct & Save" loyalty programme. Converting just 10% of agent-based users to direct customers reclaims **£15k+ annually.**

### B. ⏱️ Operational Efficiency (Peak & Trough Planning)
**The Data:** March and October are peaks; September sees a 45% drop-off.
*   **Solution:** Implement a **Predictive Staffing Model**. Use data to hire contractors 30 days in advance for peaks, eliminating emergency overtime costs. Use August "Flash Sales" to smooth the September revenue gap.

### C. 🚀 Revenue Growth (Targeted Marketing)
**The Data:** The 18-35 age group is the primary revenue "Whale" (£40,950).
*   **Solution:** Reallocate 15% of broad-spectrum ad-spend toward precision social-media retargeting for the 18-35 and >60 demographics to maximise ROAS (Return on Ad Spend).
</details>

---

## 📊 Interactive Analysis & UX
I applied the **"3-Second Rule"** to the UI design, ensuring executives can identify the "Health" of the business instantly.

![Filtered Dashboard](dashboard_filtered.png)

*   **Dynamic Slicers:** Stakeholders can slice by Room Type, Booking Source, and Status for a 1-click transition from macro trends to micro bottlenecks.
*   **Data Integrity:** Developed filters to exclude cancelled bookings, ensuring financial reports reflect actualised revenue.

---

## 🛠️ The Technical Engine
I engineered this as an enterprise-grade BI implementation, prioritizing **scalability** and **clean architecture**.

### 🧠 Data Modelling (Star Schema)
To ensure high performance across 147k+ rows, I implemented a **1-to-Many Relational Model**. This prevents "Data Bloat" and maintains referential integrity between the `Guests` and `Bookings` tables.

![Data Model](data_model.png)

### 📈 Advanced DAX Implementation
Below is a sample of the analytical logic used to drive the dashboard:

```dax
// 1. Dynamic count filtering out cancellations to maintain financial integrity
Completed bookings = 
CALCULATE(
    COUNTROWS(Bookings),
    Bookings[Booking Status] = "Completed"
)

// 2. Extracting guest behavior via Mean Length of Stay
Avg Duration Days = 
AVERAGEX(
    FILTER('Bookings', 'Bookings'[Booking Status] = "Completed"),
    DATEDIFF('Bookings'[Check-in Date], 'Bookings'[Check-out Date], DAY)
)
```
## 🏆 Core Competencies Demonstrated

*   **Scalability:** Processed 147,000+ records with zero performance degradation, ensuring enterprise-level dashboard responsiveness.
*   **Automation:** Developed an end-to-end Power Query (M) pipeline, reducing manual data-entry and reporting overhead by an estimated **5 hours per week**.
*   **Financial Logic:** Successfully translated complex statistical "noise" into a validated **£15k+ revenue recovery strategy**.
*   **Systems Thinking:** Applied 1st-principle engineering logic to data architecture, ensuring a robust, scalable Star-Schema relationship model.

## ⚙️ Setup & Reproduction

1.  Download the `Hospitality_Revenue_Analysis.pbix` file from this repository.
2.  Open the file in **Power BI Desktop** to explore the full interactivity, custom DAX measures, and relational data model.
3.  *Note: All raw data has been fully anonymised to ensure 100% GDPR compliance.*

---
*This project was completed as part of the Professional Certificate in Data Analytics & AI (Code Institute).*
