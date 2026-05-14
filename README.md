# NBA-Positional-Suitability-Analysis
# NBA Player Data (2020-2025)

## Project Overview
This project focuses on evaluating and classifying the suitability of NBA players for specific playing positions based on their regular-season statistical performance. By analyzing data from five consecutive seasons (2020–2021 to 2024–2025), we built a machine learning framework to calculate the probability of a player fitting into the five traditional roles: PG, SG, SF, PF, and C.

The project highlights the transition in modern basketball, where "hybrid roles" and "small-ball" tactics make traditional position boundaries increasingly fluid.

## Dataset
- **Sources:** Data was scraped and integrated from [Basketball-Reference](https://www.basketball-reference.com/) and [NBA Stats](https://www.nba.com/stats).
- **Timeframe:** 5 seasons (2020–2021 to 2024–2025).
- **Size:** 2,825 records with 73 initial attributes.
- **Data Layers:**
  - **Bronze:** Raw consolidated data.
  - **Silver:** Cleaned data (handling missing values, text normalization, and per-game normalization).
  - **Gold:** Feature-engineered data (log-transformed for outliers and Z-score scaled).

## Methodology
1. **Data Preprocessing:** - Filtered players with >10 games played and >5 minutes per game to ensure statistical significance.
   - Selective Log-transformation for skewed features (||skewness|| > 1).
   - Dimension reduction from 89 to 51 features.
2. **Exploratory Data Analysis (EDA):** Investigated trends in 3P%, 2P% efficiency, and Time of Possession across positions.
3. **Modeling:** Compared three classification algorithms:
   - Logistic Regression (Baseline)
   - Random Forest
   - **Support Vector Machine (SVM):** Selected as the final model for its stability in handling overlapping features of hybrid players.

## Key Features
- **PositionProbability Function:** A specialized tool developed to visualize the probability distribution of a player's role using a pie chart. It allows for an intuitive understanding of "position-less" players who contribute across multiple roles (e.g., Stephen Curry's role shifts over the years).

## Repository Structure
```text
├── data/
│   ├── raw/                # Raw crawled CSV files (2020-2025)
│   └── processed/          # Cleaned and feature-engineered dataset
├── notebooks/
│   ├── 01_data_cleaning_merging.ipynb     # Script for merging multiple seasons
│   └── 02_feature_engineering_ml.ipynb    # Script for EDA, Model training, and Analysis
├── docs/
│   ├── NBA_Final_Report.pdf               # Detailed academic report (IEEE format)
│   └── Project_Presentation.pdf           # Presentation slides
└── README.md
```

## Results
The SVM model achieved a stable classification performance, particularly in distinguishing clear roles like Center (C) and Point Guard (PG) with high precision (>80%).

The model effectively identified the "blurring" boundaries between SF, PF, and SG positions, reflecting the modern "hybrid" tactical trend in the NBA.

## Acknowledgements & Contributors

**Project Authors (Data Science Students):**
- Doan Nhat Hung
- Bui Ngoc Hoan

**Project Supervisors / Advisors:**
- **Dr. Nguyen Gia Tuan Anh** - **B.Sc. Tran Quoc Khanh** *Faculty of Information Science and Engineering, University of Information Technology (UIT - VNU-HCM)*
