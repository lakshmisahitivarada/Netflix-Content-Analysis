# Netflix Content Strategy — Analysis Report

**Author:** Sahiti  
**Dataset:** Netflix Movies and TV Shows (Kaggle)  
**Tools:** Python (Pandas, NumPy, Matplotlib, Seaborn), Power BI  
**Records Analyzed:** 8,807 titles  

---

## 1. Executive Summary

This report presents a comprehensive analysis of Netflix's content catalog, covering 8,807 titles spanning movies and TV shows added to the platform through 2021. The analysis explores content type distribution, genre popularity, geographic concentration, audience ratings, and release trends to surface actionable insights for content strategy decisions.

**Three headline findings:**

1. Netflix's catalog is movie-heavy — nearly 70% of titles are films, yet TV shows are growing in strategic importance.
2. The US contributes roughly 32% of all content, creating geographic concentration risk that diversification can address.
3. Most TV shows have only one season, suggesting an opportunity to invest in multi-season renewals for retention.

---

## 2. Dataset Overview

### Source
Netflix Movies and TV Shows dataset (publicly available on Kaggle, CC0 license).

### Original Features
`show_id`, `type`, `title`, `director`, `cast`, `country`, `date_added`, `release_year`, `rating`, `duration`, `listed_in`, `description`

### Engineered Features
| Feature | Description |
|---------|-------------|
| `year_added` | Year the title was added to Netflix |
| `month_num` | Month number of addition |
| `month_name` | Month name of addition |
| `content_age` | Years since original release |
| `duration_num` | Numeric duration value |
| `duration_unit` | Unit: "min" for movies, "Season(s)" for TV Shows |

### Data Quality Issues Found and Resolved

| Issue | Resolution |
|-------|------------|
| Missing `director` (29.9%) | Filled with "Unknown" |
| Missing `country` (9.44%) | Filled with "Unknown" |
| Missing `cast` (9.22%) | Filled with "Unknown" |
| Missing `rating` (0.05%) | Filled with "Not Rated" |
| Missing `duration` (0.03%) | Filled with "Unknown" |
| 3 rows with runtime in `rating` column | Moved duration to `duration` column, set rating to "Not Rated" |
| `date_added` as string | Converted to datetime |
| `duration_num` as string | Converted to numeric |

No duplicate rows were found in the dataset.

---

## 3. Content Type Distribution

Netflix's catalog consists of:
- **6,131 Movies** (69.62%)
- **2,676 TV Shows** (30.38%)

Movies account for nearly 7 in 10 titles on the platform. This reflects Netflix's historical roots in film licensing and its ongoing volume of film acquisitions. However, original TV series (such as Stranger Things, Squid Game, and The Crown) tend to drive the most subscriber engagement and retention, suggesting that TV Show investment may yield outsized strategic returns relative to its current catalog share.

---

## 4. Content Growth Over Time

Content additions to Netflix were negligible before 2010. The trajectory changed dramatically after 2015, driven by:

- Netflix's international market expansion (launched in 130+ countries in 2016)
- Growth in original productions
- Competitive pressure from other streaming entrants driving content volume

Peak additions occurred in 2019–2020. The 2021 figure shows a slight dip, likely attributable to production slowdowns caused by the COVID-19 pandemic affecting filming schedules globally.

**Implication:** Netflix's growth is not linear — it comes in waves tied to strategic expansion decisions. Future catalog growth will depend on content deals and originals pipeline velocity.

---

## 5. Geographic Distribution

### Top 10 Countries by Content Volume

The US alone accounts for approximately 32% of total catalog content. India ranks second, largely driven by Bollywood films and Indian original productions. The United Kingdom, Japan, and South Korea round out the top five.

**Key observation:** A significant portion of titles list multiple countries of production (co-productions). The country field was exploded to count all contributing nations.

**Strategic implication:** Geographic concentration in the US creates content dependency risk. Expanding investment in South Korea (K-dramas have shown extraordinary global viewership), Latin America, Southeast Asia, and Africa would diversify sourcing and tap into new audience demographics.

---

## 6. Genre Analysis

Genres on Netflix are multi-label — a single title may appear in 2–4 genre categories. After exploding this field, the top individual genres are:

| Rank | Genre | Count |
|------|-------|-------|
| 1 | Dramas, International Movies | 362 |
| 2 | Documentaries | 359 |
| 3 | Stand-Up Comedy | 334 |
| 4 | Comedies, Dramas, International Movies | 274 |
| 5 | Dramas, Independent Movies | 252 |
| 6 | Kids' TV | 220 |

Drama (especially international) is the single most represented genre type. Documentaries and Stand-Up Comedy show unexpectedly high volumes, reflecting Netflix's role as a major platform for non-fiction content and comedy specials.

---

## 7. Audience Rating Analysis

| Rating | Count | Audience |
|--------|-------|---------|
| TV-MA | 3,207 | Mature (17+) |
| TV-14 | 2,160 | Age 14+ |
| TV-PG | 863 | Parental Guidance |
| R | 799 | Restricted (17+) |
| PG-13 | 490 | Age 13+ |
| TV-Y7 | 334 | Age 7+ |
| TV-Y | 307 | All children |
| PG | 287 | Parental Guidance |

Mature ratings (TV-MA + TV-14 + R) account for over 65% of the catalog. Netflix's platform skews heavily adult. Content for families and children (TV-Y, TV-Y7, PG, TV-PG) is available but underrepresented relative to mature content.

**Implication:** Netflix Kids is a strategic priority for family plan subscribers. Expanding high-quality family content could reduce churn from households with children who might otherwise move to Disney+ or Apple TV+.

---

## 8. Movie Duration Analysis

Analysis limited to the 6,131 movies (TV Show duration represents seasons, not runtime).

- **Minimum:** 3 minutes (short films)
- **Maximum:** 312 minutes
- **Mean:** ~99 minutes
- **Most common range:** 80–120 minutes

The distribution follows a roughly normal curve centered around standard feature-film length. Very few titles are under 60 minutes (short films/specials) or over 150 minutes (epics).

**Implication:** Netflix movie runtime aligns with industry norms. There may be an opportunity to experiment with shorter-format films (~50–70 min) targeting mobile-first audiences.

---

## 9. Actor & Director Analysis

### Top Actors

After exploding multi-cast entries and filtering out "Unknown" values, actors from Indian cinema dominate the top-10 list by appearance count, with some appearing in 35–45 titles. This reflects the sheer volume of Indian content on the platform.

### Top Directors

Similarly, documentary filmmakers and Bollywood directors appear most frequently, with the most prolific directing 15–20+ titles. Documentary format enables faster production cycles, which naturally elevates director title counts.

**Implication:** Talent partnerships with high-volume directors and actors in key regions can serve as a low-cost lever for catalog expansion.

---

## 10. TV Show Season Analysis

| Seasons | Count |
|---------|-------|
| 1 | ~1,793 |
| 2 | ~425 |
| 3 | ~201 |
| 4+ | Declining |

The vast majority of TV shows on Netflix have a single season. This can mean:
- Limited series (designed as one-season stories)
- Shows that were cancelled after one season
- Recently launched shows that haven't been renewed yet

**Mean seasons:** ~1.76

**Strategic implication:** Investing in the renewal of high-performing shows beyond Season 1 is one of the most effective retention levers available. "Appointment viewing" around multi-season shows drives subscription continuity.

---

## 11. Monthly Content Addition Patterns

Content is not added to Netflix uniformly throughout the year. Historically higher addition months include **July** (summer viewing peak) and **December–January** (holiday and New Year period). Spring months (April–May) tend to see lower additions.

**Implication:** New content launches should be timed to align with these high-engagement windows. Marketing spend and algorithmic promotion should be intensified during peak months.

---

## 12. Recommendations

### R1 — Geographic Diversification
Reduce US-centric content concentration by accelerating acquisition from South Korea, Southeast Asia, Latin America, and Africa. Global originals like Squid Game demonstrate that non-English content can achieve mainstream global success.

### R2 — Invest in Multi-Season TV Shows
With most TV shows containing only one season, Netflix should identify top-performing first-season shows and fast-track renewal decisions. Multi-season investments drive the subscriber loyalty needed to reduce churn.

### R3 — Expand Family & Kids Content
Mature-rated content represents 65%+ of the catalog. To compete with Disney+ and Apple TV+ for family subscribers, Netflix should meaningfully grow its TV-Y, TV-Y7, and family-genre catalog.

### R4 — Strategic Release Timing
Align major content releases with historically high-traffic months (July, December, January). Use data-driven scheduling to maximize opening-week viewership.

### R5 — Support Emerging Genres
Stand-Up Comedy and Documentaries both show strong representation and likely strong viewership-per-title. Continued investment in these formats supports a valuable and underserved niche audience segment.

---

## 13. Conclusion

Analysis of 8,807 Netflix titles reveals a platform with a movie-heavy, US-centric, mature-audience-oriented catalog that underwent rapid expansion between 2015 and 2020. Drama and international content are the most represented genres, while TV Shows — despite being fewer in number — represent a significant strategic opportunity given their retention potential.

The data supports a content strategy that prioritizes geographic diversification, multi-season TV investments, and targeted growth in family and children's programming. Combined with strategic release timing, these moves can help Netflix deepen audience engagement and reduce subscriber churn in an increasingly competitive streaming landscape.

---

*Report generated from the `netflix_cleaned.csv` dataset. All figures derived from exploratory data analysis performed in `netflix-1.ipynb`.*
