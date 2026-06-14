# Netflix Content Strategy Analysis

![Netflix](https://img.shields.io/badge/Netflix-Content%20Analysis-E50914?style=for-the-badge&logo=netflix&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)

## Project Overview

This project analyzes Netflix's content catalog of **8,803 titles** to uncover patterns in content type, genre, country of origin, audience ratings, and growth trends. The insights generated support strategic decisions around content acquisition, production planning, and global expansion.

---

## Business Problem

Netflix continuously expands its library through acquisitions and original productions. Understanding what content exists — and how it's distributed across type, genre, country, and time — helps answer questions like:

- Where should Netflix invest next?
- Which countries and genres are underserved?
- What audience segments dominate the platform?

---

## Key Findings

| Metric | Value |
|--------|-------|
| Total Titles | 8,803 |
| Total Movies | 6,131 (69.6%) |
| Total TV Shows | 2,676 (30.4%) |
| Total Directors | 4,529 |
| Average Content Age | 12 Years |
| Latest Release Year | 2021 |
| Top Rating | TV-MA (3,207 titles) |
| Top Country | United States (2,818 titles) |

### Highlights
- **Movies dominate** — 69.6% of the catalog is films
- **Rapid growth after 2015** — content additions surged with Netflix's global expansion
- **US leads** content production, followed by India and the UK
- **Drama & International Movies** are the most represented genres
- **Mature ratings** (TV-MA, TV-14) make up the majority of titles
- **Most TV shows have only 1 season**, indicating a preference for limited series

---

## Project Structure

```
netflix-content-analysis/
│
├── netflix-1.ipynb                          # Jupyter Notebook (EDA + Cleaning)
├── netflix_cleaned.csv                      # Cleaned dataset (output of notebook)
├── Netflix_Content_Analysis_Dashboard.pbix  # Power BI Dashboard
├── Netflix_Content_Analysis_Dashboard.pdf   # Dashboard export (PDF)
├── Business_Questions.md                    # 11 business questions with answers
├── Netflix_Analysis_Report.md               # Full analysis report
├── Netflix_Content_Analysis.pptx            # Presentation deck
└── README.md                                # This file
```

---

## Tools & Technologies

| Tool | Purpose |
|------|---------|
| Python (Pandas, NumPy) | Data cleaning & exploration |
| Matplotlib / Seaborn | Data visualization |
| Jupyter Notebook | Interactive analysis environment |
| Power BI | Interactive dashboard |
| CSV | Cleaned data export |

---

## Dataset

- **Source:** [Netflix Movies and TV Shows – Kaggle](https://www.kaggle.com/datasets/shivamb/netflix-shows)
- **Records:** 8,807 titles
- **Features:** 12 original columns + 6 engineered features
- **Time Range:** Titles from 1925 to 2021

### Engineered Features
- `year_added` — Year the title was added to Netflix
- `month_num` / `month_name` — Month the title was added
- `content_age` — Years since release (`current year − release_year`)
- `duration_num` — Numeric duration (minutes for movies, seasons for TV shows)
- `duration_unit` — Unit of duration

---

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/netflix-content-analysis.git
   cd netflix-content-analysis
   ```

2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```

3. Launch the notebook:
   ```bash
   jupyter notebook netflix-1.ipynb
   ```

4. Open `Netflix_Content_Analysis_Dashboard.pbix` in **Power BI Desktop** to explore the interactive dashboard.

---

## Dashboard Preview

The Power BI dashboard includes:
- KPI cards (Total Titles, Movies, TV Shows, Directors, Avg Content Age)
- Top Countries by Content Type (bar chart)
- Content Rating Distribution
- Content Released by Year (line chart)
- Top Genres (bar chart)
- Movies vs TV Shows split (donut chart)

---

## Analysis Questions Answered

1. Does Netflix offer more Movies or TV Shows?
2. How has Netflix's content catalog grown over time?
3. Which countries contribute the most content?
4. Which genres are most common?
5. What audience ratings dominate the catalog?
6. How has content production changed over time?
7. What is the typical duration of Netflix movies?
8. Which actors appear most frequently?
9. Which directors have the most titles?
10. How many seasons do Netflix TV Shows typically have?
11. During which months is content most frequently added?

---

## Recommendations

1. **Diversify content geographically** — reduce heavy dependence on US content by expanding acquisitions from emerging markets (Southeast Asia, Latin America, Africa)
2. **Invest in multi-season shows** — the majority of TV Shows have only one season; long-running series improve subscriber retention
3. **Lean into Drama & International** — these top genres indicate strong audience demand
4. **Strategic release timing** — align new content drops with historically high addition months
5. **Expand family & children's content** — kids' ratings (TV-Y, TV-Y7, PG) are underrepresented relative to mature content

---

## Author

**Sahiti**
- Data Analyst | Python | Power BI | SQL
- [LinkedIn](#) | [GitHub](#)

---

## License

This project is for educational and portfolio purposes. The dataset is publicly available on Kaggle under the CC0 license.
