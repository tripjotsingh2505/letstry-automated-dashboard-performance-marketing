<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code\&weight=600\&size=32\&pause=1000\&color=2E9EF7\&center=true\&vCenter=true\&width=650\&lines=InsightIQ+Dashboard;Sales+%26+Campaign+Analytics;ROAS+%2F+ROI+Insights+at+a+Glance;Built+with+Streamlit+%2B+Plotly" alt="Typing SVG" />

<br/>

[!\[Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge\&logo=streamlit\&logoColor=white)](https://streamlit.io/)
[!\[Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge\&logo=python\&logoColor=white)](https://www.python.org/)
[!\[Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge\&logo=pandas\&logoColor=white)](https://pandas.pydata.org/)
[!\[Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge\&logo=plotly\&logoColor=white)](https://plotly.com/)
[!\[License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](#license)

**An interactive Streamlit dashboard for analyzing sales campaign performance —
upload a file and get instant KPIs, ROAS/ROI breakdowns, charts, and actionable recommendations.**

</div>

\---

## 📌 Overview

InsightIQ Dashboard turns a raw sales export (CSV/Excel) into a fully interactive analytics dashboard in seconds. It automatically computes sales and ROAS metrics, flags underperforming campaigns and targeting types, lets you drill into exactly which keywords are dragging down performance, and exports the results as a ready-to-share CSV — no manual pivot tables required.

\---

## ✨ Features

### 📂 Data Handling

* Upload `.csv` or `.xlsx` files directly
* One-click **Preprocess** step computes `Total Sales = Direct Sales + Indirect Sales`
* Automatic date parsing and cleanup of invalid rows

### 🎛️ Filtering

* Date range presets — Today, Yesterday, Last 7 Days, Last 30 Days, or a Custom Range
* Filter by Campaign Name, Targeting Type, and Targeting Value

### 📊 Campaign Insights Summary

* Total Campaigns, Total Budget Spend, Avg Sales per Campaign, and **Total ROAS Across Campaigns** (Total Sales ÷ Total Budget Spend)

### 🧭 Strategic Recommendations

* Best-performing targeting type (by impressions), targeting value (by sales), and campaign (by ROAS)
* **Risky Campaigns** — flagged when `ROAS < 3` and `Budget Spent > 1,000`, sorted by budget spend (highest to lowest)
* Each risky campaign expands into a **drill-down table** of its own targeting values that also have `ROAS < 3`, with full metrics: Most Viewed Position, Impressions, Total Sales, Estimated Budget Consumed, CPM, and ROAS
* **📥 One-click CSV export** of every risky campaign paired with its risky targeting values — ready to share or archive
* **Risky Targeting Types** — same thresholds, applied across the full filtered dataset, sorted by budget spend

### 📈 Visualizations

|Chart|Insight|
|-|-|
|Total Sales Trend|Sales performance over time|
|Sales by Campaign|Which campaigns drive revenue|
|Budget Consumed by Campaign|Where spend is concentrated (highest to lowest)|
|ROI by Targeting Type|Efficiency across targeting strategies|
|Sales Share by Targeting Type|Revenue mix (pie chart)|
|Sales by Budget Range|High / Medium / Low spend performance|

### 📋 Tables

All ROAS-based tables include: **Most Viewed Position, Impressions, Total Sales, Estimated Budget Consumed, CPM, and ROAS** — sorted by Estimated Budget Consumed (highest to lowest).

* Filtered data table (irrelevant columns auto-hidden)
* Sales by Budget Range (thresholds vary by Targeting Type)
* Top 5 Campaigns by Total Sales
* Top 5 Campaigns by ROAS
* Campaigns with ROAS less than 3

\---

## 🗂️ Required Columns

|Column|Type|Notes|
|-|-|-|
|`Date`|Date|Expected format `DD-MM-YYYY`|
|`Campaign Name`|Text||
|`Targeting Type`|Text|e.g. `Category`, `Keyword`|
|`Targeting Value`|Text||
|`Direct Sales`|Number|Used to compute `Total Sales`|
|`Indirect Sales`|Number|Used to compute `Total Sales`|
|`Estimated Budget Consumed`|Number|Used for ROAS/ROI/CPM calculations|
|`Impressions`|Number|Optional — enables CPM and the "high impressions" recommendation|
|`Most Viewed Position`|Text|Optional — shown in ROAS drill-down tables|

> If `Impressions` or `Most Viewed Position` are missing from your file, the dashboard gracefully falls back to `0` / `N/A` for those fields instead of breaking.

\---

## 🚀 Getting Started

### 1\. Clone the repository

```bash
git clone <your-repo-url>
cd <your-repo-folder>
```

### 2\. Install dependencies

```bash
pip install -r requirements.txt
```

**requirements.txt**

```
streamlit
pandas
plotly
openpyxl
```

### 3\. Run the app

```bash
streamlit run final\_app.py
```

### 4\. Use it

1. Upload your sales CSV or Excel file
2. Click **Preprocess** to generate the `Total Sales` column
3. Filter by date, campaign, or targeting in the sidebar
4. Review the Strategic Recommendations, expand any risky campaign to see its risky keywords, and download the CSV if you need to share it

\---

## ⚙️ Configuration Notes

* Rows with unparseable dates are automatically dropped
* ROAS/ROI/CPM calculations exclude rows where `Estimated Budget Consumed` or `Impressions` is `0`, to avoid division-by-zero errors
* The `ROAS < 3` and `Budget > 1,000` thresholds used across the risk flags are defined directly in `final\_app.py` and can be adjusted there
* The CSV export includes only campaigns that have at least one targeting value with `ROAS < 3`

\---

## 🛠️ Tech Stack

* [**Streamlit**](https://streamlit.io/) — dashboard framework
* [**Pandas**](https://pandas.pydata.org/) — data processing
* [**Plotly Express**](https://plotly.com/python/plotly-express/) — interactive charts

\---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

\---

<div align="center">

Made with ❤️ using Streamlit

</div>

