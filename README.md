# 📊 GA4 Website Traffic Performance Analysis

> A comprehensive end-to-end data analytics project using Google Analytics 4 (GA4) data — from raw export to Python EDA and an interactive Power BI dashboard.

![Power BI Dashboard](Website.png)

---

## 📑 Table of Contents

1. [Project Overview](#project-overview)
2. [Key Metrics & Highlights](#key-metrics--highlights)
3. [Tech Stack](#tech-stack)
4. [Project Structure](#project-structure)
5. [Dataset Description](#dataset-description)
6. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
7. [Power BI Dashboard](#power-bi-dashboard)
8. [Key Insights & Findings](#key-insights--findings)
9. [Recommendations](#recommendations)
10. [How to Run](#how-to-run)
11. [Requirements](#requirements)
12. [Author](#author)

---

## Project Overview

This project analyzes website traffic and user engagement data exported from **Google Analytics 4 (GA4)** for the period **April 6, 2026 – May 3, 2026**. The goal is to understand how users arrive at the website, how they engage across different channels, and when peak traffic occurs — ultimately providing actionable insights to improve digital marketing strategy.

The project covers:
- **Data Cleaning & Preprocessing** in Python (Pandas)
- **Exploratory Data Analysis** with Matplotlib & Seaborn
- **Interactive Dashboard** built in Microsoft Power BI

---

## Key Metrics & Highlights

| Metric | Value |
|---|---|
| 📅 Date Range | Apr 6, 2024 – May 3, 2024 |
| 👥 Total Users | 133,440 |
| 🔗 Total Sessions | 162,895 |
| ⚡ Total Events | 770,911 |
| ✅ Engaged Sessions | 90,132 |
| 📈 Avg. Engagement Rate | 50.3% |
| 📊 Channel Groups Tracked | 7 |
| 🗃️ Dataset Size | 3,182 rows × 10 columns |

---

## Tech Stack

| Tool | Purpose |
|---|---|
| **Python 3.x** | Data cleaning, EDA, visualizations |
| **Pandas** | Data manipulation |
| **Matplotlib / Seaborn** | Statistical plots |
| **NumPy** | Numerical operations |
| **Microsoft Power BI** | Interactive dashboard |
| **Google Analytics 4** | Data source |
| **Jupyter Notebook** | Development environment |

---

## Project Structure

```
ga4-traffic-analysis/
│
├── data-export (1).csv        # Raw GA4 data export
├── website.ipynb              # Jupyter Notebook — EDA & visualizations
├── requirements.txt           # Python dependencies
├── Website.png                # Power BI dashboard screenshot
├── project_report.pdf         # Full project report
└── README.md                  # This file
```

---

## Dataset Description

The dataset was exported directly from Google Analytics 4 and contains **3,182 rows** of hourly, channel-level data.

| Column | Description |
|---|---|
| `channel group` | Traffic channel (Direct, Organic Search, etc.) |
| `DateHour` | Timestamp in YYYYMMDDHH format |
| `Users` | Unique users in that hour/channel |
| `Sessions` | Total sessions |
| `Engaged Sessions` | Sessions with meaningful interaction (≥10s or ≥1 event) |
| `Avg engagement time per session` | Average seconds of active engagement |
| `Engaged sessions per user` | Ratio of engaged sessions to users |
| `Events per session` | Average number of events fired per session |
| `Engagement rate` | Proportion of sessions that were engaged |
| `Event count` | Total events fired |

**Channel Groups present:** Direct, Organic Social, Organic Search, Referral, Unassigned, Organic Video, Email

---

## Exploratory Data Analysis (EDA)

The Jupyter Notebook (`website.ipynb`) performs the following analyses:

**1. Data Cleaning**
- Parsed `DateHour` from YYYYMMDDHH format to datetime
- Converted all numeric columns from string to float/int
- Extracted `Hour` feature for temporal analysis
- Confirmed zero null values

**2. Sessions & Users Over Time**
- Line chart tracking daily fluctuations across the study period

**3. Total Users by Channel Group**
- Bar chart comparing user volume per acquisition channel

**4. Average Engagement Time by Channel**
- Bar chart of mean engagement duration per channel

**5. Engagement Rate Distribution**
- Box plot showing spread and outliers per channel

**6. Engaged vs. Non-Engaged Sessions**
- Stacked bar chart revealing how effectively each channel converts visits

**7. Traffic Heatmap by Hour & Channel**
- Seaborn heatmap (Hour × Channel) identifying peak activity windows

**8. Engagement Rate vs. Sessions Over Time**
- Dual-line chart correlating session volume with engagement quality

---

## Power BI Dashboard

The Power BI dashboard provides an interactive, filterable view of all key metrics.

**Filters:** Date Range · Channel Group · Device Category · Source/Medium

**Visuals included:**
- KPI Cards — Users, Sessions, Events, Engaged Sessions, Avg Engagement Time (with MoM % change)
- Channel Group vs Users — Horizontal bar chart
- Channel Group vs Engagement Rate — Vertical bar chart
- Date Hour vs Users — Time series
- Date Hour vs Sessions — Time series

**May 2024 Snapshot:**

| Metric | May 2024 | vs. April 2024 |
|---|---|---|
| Users | 47.2K | ▲ 12.5% |
| Sessions | 57.5K | ▲ 9.3% |
| Events | 248.7K | ▲ 18.6% |
| Engaged Sessions | 32.6K | ▲ 11.7% |
| Avg Engagement Time | 01:32 | ▼ -4.8% |

---

## Key Insights & Findings

### Channel Performance

- **Organic Social** drives the most users (47,572) but has a moderate engagement rate of 54.1%, suggesting users browse but don't always convert deeply.
- **Referral** traffic has the **highest engagement rate (66.1%)** despite lower volume — indicating high-intent visitors from trusted sources.
- **Organic Search** delivers a strong balance of volume and quality (57.9% engagement rate).
- **Direct** traffic is high volume but engagement lags at 45.6%.
- **Organic Video** has the best engagement rate (76%) but minimal volume — an underdeveloped channel.
- **Unassigned** traffic (540 users, 0.75% engagement rate) indicates a UTM parameter/tagging issue.

### Temporal Patterns

- Traffic peaks consistently during **business hours (9 AM – 6 PM)** and mid-week days.
- May 2024 showed growth across almost all metrics compared to April 2024.
- **Average Engagement Time dropped 4.8%** despite higher session counts — a content or UX quality signal.

---

## Recommendations

1. **Fix Unassigned Traffic** — Audit UTM parameters and GA4 configuration to restore attribution.
2. **Invest in Referral Partnerships** — Highest engagement rate; identify and nurture these sources.
3. **Scale Organic Video** — 76% engagement rate makes video a high-ROI opportunity.
4. **Address Engagement Time Drop** — Audit top landing pages for content quality and UX issues.
5. **Optimize for Peak Hours** — Align social posts, email campaigns, and ad spend to 9 AM – 6 PM weekdays.
6. **Develop Email Channel** — Only 2 users came via Email; implement a proper email marketing strategy.

---

## How to Run

**1. Clone the repository**
```bash
git clone https://github.com/YOUR_USERNAME/ga4-traffic-analysis.git
cd ga4-traffic-analysis
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

**3. Launch the Jupyter Notebook**
```bash
jupyter notebook website.ipynb
```

> **Note:** Update the `pd.read_csv()` path in the notebook to point to your local copy of the data file.

---

## Requirements

See `requirements.txt` for the full dependency list.

---

## Author

**[Muhammad Faham Tariq]**
- 📧 faham7106@gmail.com
- 💼 [LinkedIn](https://www.linkedin.com/in/nishant015/)
- 🐙 [Insatgram](https://www.instagram.com/inishantindia/?hl=en)

---

*Data Source: Google Analytics 4 | Visualization: Microsoft Power BI*
