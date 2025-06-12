# 🏏 Cricket Analytics with PySpark

## 📌 Project Overview
This project uses PySpark to perform data preprocessing and analysis on cricket match data. The goal is to extract insights from detailed ball-by-ball, player, and match-level data using Spark SQL and DataFrame APIs.

---

## 📂 Data Sources
The following datasets are used:

- `ball_by_ball`: Ball-level delivery data
- `match`: Match-level metadata including teams, date, venue, and results
- `player`: Player master data including birthdate and skills
- `player_match`: Player performance and role in each match
- `team`: Team ID and name mappings

---

## 🧹 Data Preparation

Key transformation steps:

- **Data type casting**: Ensured correct column types (`IntegerType`, `DateType`, `StringType`)
- **Invalid delivery filtering**: Excluded deliveries like wides and no-balls for certain analyses
- **Feature engineering**:
  - Extracted `year`, `month`, and `day` from match dates
  - Created `high_impact` flag for wickets or high-run deliveries
  - Classified players as `Veteran` if age ≥ 35
  - Categorized win margins as `High`, `Medium`, or `Low`
  - Standardized player names and filled missing values
- **Window functions**: Used to compute running total of runs by innings

---

## 📊 Analytical Insights

### 🏅 Top Scoring Batsmen by Season
Aggregate total runs scored by each batsman per season.

### 🎯 Economical Bowlers in Powerplay
Identifies bowlers with the lowest average runs per ball in the first 6 overs.

### 🎲 Toss Impact
Analyzes the correlation between winning the toss and winning the match.

### 🧮 Average Runs in Winning Matches
Shows average runs scored by players in matches won by their team.

---

## 📉 Visualizations

- **Top 10 Economical Bowlers in Powerplay**:
  - Bar chart created using `matplotlib`
  - Shows bowlers with the best economy during overs 1–6

---

## 🧠 Advanced Transformations

- `running_total`: Tracks cumulative runs in an innings using window functions
- `high_impact`: Flags impactful deliveries (wickets or >6 total runs)
- `win_margine_category`: Categorizes win margins into `High`, `Medium`, and `Low`
- `veteran_status`: Labels players as `Veteran` (age ≥ 35) or `Non-Veteran`
- `years_since_debut`: Calculates experience based on debut year and current date

---

## 💻 Technologies Used

- Apache Spark (PySpark)
- Spark SQL
- Databricks or local Spark cluster
- Pandas
- Matplotlib

---

## 🚀 How to Run

1. Ensure your Spark environment is configured with access to all required tables.
2. Open the notebook and run cells sequentially.
3. Modify SQL or DataFrame logic as needed for custom analysis.

---

## 📁 Folder Structure (Optional Suggestion)


