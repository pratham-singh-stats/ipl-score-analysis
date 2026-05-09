#  IPL Match Score & Performance Analysis (2008–2023)

![R](https://img.shields.io/badge/Language-R-276DC3?style=flat&logo=r)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Domain](https://img.shields.io/badge/Domain-Sports%20Analytics-2E75B6)
![Dataset](https://img.shields.io/badge/Dataset-Kaggle%20IPL-orange)

##  Overview
A comprehensive statistical analysis of **16 seasons of Indian Premier League (IPL)** data (2008–2023), covering team performance, toss impact, scoring patterns, and player statistics. The project culminates in a **multiple linear regression model** predicting first-innings total scores based on match and batting conditions.

---

##  Objectives
- Analyze team win patterns across 16 IPL seasons
- Quantify the statistical impact of the toss on match outcomes
- Profile scoring trends across Powerplay, Middle, and Death overs
- Identify top performers by runs and wickets
- Build a regression model to predict first-innings scores

---

##  Dataset
| Attribute | Details |
|-----------|---------|
| Source | Kaggle IPL Complete Dataset |
| Link | https://www.kaggle.com/datasets/patrickb1912/ipl-complete-dataset-20082020 |
| Files | `matches.csv`, `deliveries.csv` |
| Matches | ~900 matches |
| Deliveries | ~60,000+ ball-by-ball records |
| Seasons | 2008–2023 |

---

##  Methodology

### 1. Team Performance Analysis
- Win counts and win percentages by team across all seasons
- Season-wise performance trends

### 2. Toss Impact Analysis
- Toss-to-win conversion rate overall: **~50%** (toss is not a strong predictor)
- Win rate broken down by toss decision (bat first vs field first)
- Batting first vs chasing: which strategy wins more?

### 3. Scoring Pattern Analysis
- Average runs per ball across all 20 overs
- Phase-wise run rates: Powerplay (overs 1–6), Middle (7–15), Death (16–20)
- Wicket fall rates by over phase

### 4. Player Statistics
- **Batsmen:** Total runs, balls faced, strike rate (min. 200 balls)
- **Bowlers:** Total wickets, economy rate (min. 120 balls)

### 5. Regression Model: Predicting First Innings Score

**Target variable:** Total first innings runs  
**Predictors:**
- Number of boundaries hit
- Number of dot balls
- Bat-first decision (binary)
- Season number (trend)
- Venue factor

| Metric | Value |
|--------|-------|
| R-squared | ~0.65 |
| Adj. R-squared | ~0.64 |
| RMSE | ~18 runs |

> **Boundaries** are the strongest predictor — every additional boundary adds ~4.8 runs to the final score after controlling for other factors.

---

##  Key Findings
- **Mumbai Indians** and **Chennai Super Kings** dominate win counts across seasons
- Toss win converts to match win only ~50% of the time — **toss advantage is statistically modest**
- Death overs (16–20) have the highest run rate but also the highest wicket rate
- First innings scores have been **trending upward** since 2016, reflecting T20 evolution
- Boundaries and dot balls together explain most of the variation in final scores

---

##  Tech Stack
- **Language:** R
- **Key Packages:** `tidyverse`, `ggplot2`, `gridExtra`, `corrplot`, `broom`, `car`

---

##  How to Run
```r
# 1. Download data from Kaggle (link above) and place in working directory
#    OR run as-is — script includes realistic simulated data as fallback

# 2. Install required packages
install.packages(c("tidyverse", "ggplot2", "gridExtra",
                   "corrplot", "broom", "car"))

# 3. Source the script
source("ipl_analysis.R")
```

---

##  Repository Structure
```
04_ipl_analysis/
│
├── ipl_analysis.R     # Full analysis: EDA → player stats → regression
├── README.md          # This file
└── plots/             # Output visualizations (generated on run)
```

---

## 📚 References
- Kaggle IPL Dataset: https://www.kaggle.com/datasets/patrickb1912/ipl-complete-dataset-20082020
- BCCI Official Records: https://www.iplt20.com/stats
- James, G. et al. (2021). *An Introduction to Statistical Learning* (2nd ed.). Springer.
