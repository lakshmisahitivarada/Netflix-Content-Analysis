# Netflix Content Analysis — Business Questions & Answers

## Project Context

Netflix operates a global streaming platform with over 8,800 titles. This document outlines the 11 key business questions explored in this analysis, the analytical approach used, and the findings for each.

---

## Q1. Does Netflix offer more Movies or TV Shows?

**Business Relevance:** Understanding the content-type split reveals Netflix's primary content strategy and investment focus.

**Approach:** Count of titles by `type` column.

**Finding:**
- Movies: **6,131 titles (69.6%)**
- TV Shows: **2,676 titles (30.4%)**

**Insight:** Movies dominate the Netflix catalog by a wide margin, reflecting the platform's strength in film acquisition and production. While TV Shows represent a significant share, movies account for nearly 7 out of 10 titles.

---

## Q2. How has Netflix's content catalog grown over time?

**Business Relevance:** Identifies periods of strategic expansion and investment activity.

**Approach:** Count of titles by `year_added` to Netflix.

**Finding:** Content additions were minimal before 2015. A sharp acceleration began around 2015–2016, with peak additions occurring around 2019–2020, followed by a slight decrease in 2021.

**Insight:** The surge after 2015 aligns with Netflix's major international expansion phase. The slowdown in 2021 may reflect the impact of COVID-19 on production pipelines.

---

## Q3. Which countries contribute the most content to Netflix?

**Business Relevance:** Highlights geographic concentration and potential gaps in global content strategy.

**Approach:** Explode the `country` column (titles can have multiple countries), then count by country.

**Finding (Top 5):**
| Country | Titles |
|---------|--------|
| United States | ~2,818 |
| India | ~972 |
| United Kingdom | ~419 |
| Japan | ~245 |
| South Korea | ~199 |

**Insight:** The US contributes roughly 3× more titles than the next largest country (India). This geographic concentration represents both a strength and a strategic vulnerability — diversifying sourcing reduces dependence on any one market.

---

## Q4. Which genres are most common on Netflix?

**Business Relevance:** Genre popularity informs content investment priorities and audience targeting.

**Approach:** Explode `listed_in` column (multi-genre field), count genre occurrences.

**Finding (Top 6 from dashboard):**
| Genre | Count |
|-------|-------|
| Dramas, International Movies | 362 |
| Documentaries | 359 |
| Stand-Up Comedy | 334 |
| Comedies, Dramas, International Movies | 274 |
| Dramas, Independent Movies | 252 |
| Kids' TV | 220 |

**Insight:** Drama (especially international) and Documentaries dominate the catalog, reflecting broad appeal strategies. Stand-up Comedy also shows strong representation, indicating dedicated audience segments for this format.

---

## Q5. What audience ratings dominate Netflix's catalog?

**Business Relevance:** Content ratings define the audience demographic being targeted and impact content acquisition decisions.

**Approach:** Count of titles by `rating` column.

**Finding (Top 5):**
| Rating | Count |
|--------|-------|
| TV-MA | 3,207 |
| TV-14 | 2,160 |
| TV-PG | 863 |
| R | 799 |
| PG-13 | 490 |

**Insight:** Mature ratings (TV-MA and TV-14) account for over 60% of titles. Netflix's catalog is heavily oriented toward adult audiences. Family and children's content (TV-Y, TV-Y7, PG) is comparatively underrepresented.

---

## Q6. How has content production changed over time?

**Business Relevance:** Release year distribution shows whether Netflix prioritizes new or classic content.

**Approach:** Count of titles by `release_year`.

**Finding:** Titles released before 2000 are minimal. Production volumes accelerate from 2000 onward, with the sharpest increase after 2010. The majority of Netflix's catalog consists of content released in the 2010s and early 2020s.

**Insight:** Netflix's catalog skews modern. The average content age is 12 years. This suggests a preference for contemporary content that aligns with current audience tastes.

---

## Q7. What is the typical duration of Netflix movies?

**Business Relevance:** Understanding runtime distribution helps assess whether Netflix content matches standard viewing habits and production norms.

**Approach:** Filter for `type == "Movie"`, analyze `duration_num` (minutes).

**Finding:**
- Most movies fall between **80 and 120 minutes**
- Mean duration is approximately **99 minutes**
- Very few titles exceed 150 minutes

**Insight:** Netflix movies align with traditional feature-film runtime conventions. This suggests the platform caters to standard audience attention spans rather than pushing unconventional formats.

---

## Q8. Which actors appear most frequently on Netflix?

**Business Relevance:** Identifying recurring actors reveals talent relationships and catalog personality.

**Approach:** Explode `cast` column, exclude "Unknown" entries, count appearances.

**Finding:** A small group of actors — particularly from Indian cinema — appear across 30–40+ titles, reflecting strong content volumes from Bollywood and regional Indian productions.

**Insight:** Recurring talent signals long-term production partnerships. Tracking top actors by region can help identify casting trends and partnership opportunities.

---

## Q9. Which directors have the most titles on Netflix?

**Business Relevance:** Prolific directors indicate recurring creative relationships and production output patterns.

**Approach:** Filter out "Unknown" directors, count titles by director.

**Finding:** Top directors appear in 15–20+ titles each, predominantly from documentary and Bollywood genres.

**Insight:** Documentary filmmakers tend to produce more titles in a shorter period due to lower production overhead. A small pool of directors drives a large share of catalog content.

---

## Q10. How many seasons do Netflix TV Shows typically have?

**Business Relevance:** Season count informs subscriber retention strategy — long-running shows drive binge behavior and loyalty.

**Approach:** Filter for `type == "TV Show"`, analyze `duration_num` (seasons).

**Finding:**
- **Majority have only 1 season**
- Mean number of seasons: ~1.76
- Shows with 5+ seasons are rare

**Insight:** Most Netflix TV shows are either limited series or recently launched. Investing in renewing high-performing shows for multiple seasons could significantly improve subscriber retention.

---

## Q11. During which months is content most frequently added to Netflix?

**Business Relevance:** Seasonal patterns in content additions reveal strategic release timing and acquisition windows.

**Approach:** Count of titles by `month_name` of `date_added`.

**Finding:** Content additions are highest in **July, December, and January**, with relatively lower volumes in spring months (April–May).

**Insight:** Netflix appears to front-load content around the summer viewing season and the holiday period — both high-engagement windows. This pattern can guide optimal timing for new releases and marketing campaigns.

---

## Summary Table

| # | Question | Key Finding |
|---|----------|-------------|
| Q1 | Movies vs TV Shows? | 69.6% Movies, 30.4% TV Shows |
| Q2 | Content growth over time? | Sharp rise after 2015 |
| Q3 | Top content countries? | USA dominates, India 2nd |
| Q4 | Most common genres? | Dramas & Documentaries lead |
| Q5 | Audience ratings? | TV-MA accounts for 36% of catalog |
| Q6 | Production trend? | Most content released post-2010 |
| Q7 | Typical movie duration? | 80–120 minutes |
| Q8 | Most frequent actors? | Indian cinema actors appear most |
| Q9 | Most prolific directors? | Documentary & Bollywood directors lead |
| Q10 | TV Show seasons? | Majority are 1-season shows |
| Q11 | Peak addition months? | July, December, January |
