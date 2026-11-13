# 📺 BrightTV Viewer Insights & Analytics Case Study

Welcome to the official repository for the **BrightTV Viewer Insights** project. This case study delivers an exploratory data analysis (EDA) of user profiles and viewership logs to uncover audience demographics, regional consumption trends, and peak viewing habits.

[![Live Dashboard](https://img.shields.io/badge/Lovable-Interactive%20Dashboard-brightgreen?style=for-the-badge&logo=appsignal)](https://brighttv-viewer-insights.lovable.app)

---

## 🚀 Interactive Dashboard
Explore the fully interactive analytics and experience platform built for this project:
👉 **[BrightTV Viewer Insights Dashboard](https://brighttv-viewer-insights.lovable.app)**

---

## 🎯 1. Business Problem & Objective
As streaming platforms scale, understanding user behavior and content consumption patterns is critical for targeted programming and resource allocation. The core business questions addressed in this case study include:
* **Who is watching?** Identifying core demographic segments (age distributions, gender splits, and regional concentrations).
* **Where is engagement highest?** Pinpointing provincial hotspots to guide regional marketing and content delivery.
* **When are peak viewing hours?** Analyzing local consumption windows (adjusted to South African Standard Time) to optimize broadcast schedules and platform traffic management.

---

## ⚙️ 2. Process & Methodology
The data pipeline was structured systematically from raw logs to clean, analysis-ready datasets using Python (`pandas`, `numpy`) and Google Colab:

1. **Data Cleaning & Quality Audit:**
   * Handled and imputed missing values within the `User Profiles` dataset.
   * Identified and removed duplicate records from the `Viewership` logs.
   * Filtered out unrealistic age outliers ($\le 5$ or $\ge 100$ years old) to ensure demographic integrity.
2. **Feature Engineering & Timezone Conversion:**
   * Converted UTC timestamps (`RecordDate2`) to **South African Standard Time (SAST, UTC+2)** (`SA_RecordDate`) to ensure accurate local time-series analysis.
   * Extracted local peak hours (`SA_Hour`), day names, and months.
   * Grouped users into standardized demographic brackets (`0-17`, `18-24`, `25-34`, `35-44`, `45-54`, `55+`).
   * Parsed text-based viewing durations into total numeric seconds (`Duration_seconds`).
3. **Dataset Integration:**
   * Performed a clean inner join on `UserID` to merge user profiles and viewership logs into a unified relational dataset (9,723 rows and 19 columns).

---

## 📊 3. Summary of Findings & Insights

* **Regional Dominance (Gauteng Hub):** Geographic analysis reveals that Gauteng serves as the primary consumption hub, accounting for the highest concentration of active viewership and user registrations.
* **Peak Consumption Windows:** Viewing activity spikes significantly during late afternoons and evenings, with weekend engagement (particularly Fridays and Saturdays) showing the highest total streaming duration.
* **Demographic Engagement:** Young adults and mid-tier age brackets form the backbone of platform engagement, demonstrating distinct preferences for specific content categories during weekend evening slots.

---

## 📁 4. Project Structure & Artifacts

```text
├── assets/
│   ├── miro_flowchart.png        # Workflow & pipeline architecture
│   └── gantt_chart.png           # Project timeline & milestone tracking
├── notebooks/
│   └── BrightTV_EDA.ipynb        # Complete exploratory data analysis script
├── README.md                     # Project documentation
