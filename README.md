

##  Global Trends in Digital Finance — Power BI Dashboard

###  Project Overview

This project explores **global financial inclusion and digital finance adoption** using the **World Bank Global Findex Database (2025)**. It investigates how regional and income-level differences affect access to financial services and evaluates how **mobile and digital technologies** help close inclusion gaps across 140 economies.

The dashboard visualises patterns in:

* Account ownership and activity
* Savings and borrowing behaviour
* Mobile and digital account usage
* Online vs. cash payment preferences
* Regional and income-level disparities

###  Research Question

> How do regional and income-level differences influence financial inclusion, and what role does digital finance play in reducing these disparities globally?

---

##  Methodology

1. **Data Source:**

   * *World Bank Global Findex Database 2025* (CSV, 2011–2024)
   * *GlobalFindex2025-glossary.xlsx* (metadata)

2. **Data Preparation:**

   * Imported via Power BI “Get Data”
   * Cleaned using Power Query:

     * Replaced “NA/N/A” with nulls
     * Removed >80% null columns
     * Normalised region labels
     * Validated 0–1 range for proportion fields

3. **Data Modelling:**

   * Flat table with implicit hierarchies (Region → Country → Year)
   * Created key **DAX measures**:

     ```DAX
     AvgAccount = AVERAGE('GlobalFindex'[account_t_d])
     MobileUsageRate = AVERAGE('GlobalFindex'[mobileaccount_t_d])
     DigitalInclusion = AVERAGE('GlobalFindex'[dig_acc])
     SavingsBorrowRatio = DIVIDE(
         AVERAGE('GlobalFindex'[saved_any_t_d]),
         AVERAGE('GlobalFindex'[borrow_any_t_d])
     )
     ```

4. **Dashboard Design:**
   Built in **Power BI Desktop (.pbix)** with:

   * KPI Cards (Account, Inactive, Mobile)
   * Regional comparison bar chart
   * Online payment donut chart
   * Income vs. digital use pie chart
   * Interactive country map
   * Government transfer summary table
   * Line chart of mobile account trends (2014–2024)
   * Region, Year, and Income slicers

---

## Key Findings

| **Finding**                           | **Insight**                                                                           |
| ------------------------------------- | ------------------------------------------------------------------------------------- |
| **1. Global inclusion is improving**  | Account ownership rose to **70%** in 2024, with **mobile accounts up to 34%**.        |
| **2. Regional gaps persist**          | Sub-Saharan Africa leads in mobile use; MENA lags behind.                             |
| **3. Informal finance remains vital** | In many countries, **family and friends** remain the main source for emergency funds. |
| **4. COD still matters**              | Cash-on-delivery ≈ 33%, paid online ≈ 17%; logistics and trust affect adoption.       |
| **5. Digital pensions emerging**      | Bank channels dominate, but **East Asia & Pacific** shows rising mobile payouts.      |
| **6. Income effect**                  | Higher-income economies show higher digital finance use.                              |

---

## 🧩 Policy & Business Implications

* **Scale mobile rails** in wallet-ready regions (SSA, EAP).
* **Activate usage**, not just accounts, in bank-centric economies (ECA).
* **Digitise safety nets** with bank→wallet options where mobile use is high.
* **Reduce COD reliance** via better refund and delivery systems.

---

## 🛠️ Tools & Technologies

* **Power BI Desktop** (Data Modelling, DAX, Visualization)
* **Power Query Editor** (ETL)
* **Microsoft Excel** (Data dictionary, validation)
* **World Bank Open Data (Global Findex 2025)**

---

## 📁 Repository Structure

```
📂 Global-Trends-Digital-Finance
 ├── report.pdf            # Full academic report
 ├── dashboard.pbix        # Power BI dashboard
 ├── screenshots/          # Dashboard preview images
 ├── data/
 │    ├── GlobalFindexDatabase2025.csv
 │    └── GlobalFindex2025-glossary.xlsx
 ├── README.md                     # (This file)
```

---


---

##  Citation

Based on:

* World Bank (2025). *Global Findex Database 2025*
* Demirgüç-Kunt et al. (2022). *Financial inclusion, digital payments, and resilience in the age of COVID-19*
* Jack & Suri (2014). *Risk Sharing and Transaction Costs: Evidence from Kenya’s Mobile Money Revolution*


