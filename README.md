# 📊 Google Play Store: Exploratory Data Analysis
**Extracting market insights from 10,000+ messy app records using Python and Pandas.**

## 🎯 The Objective
Raw data in the real world is rarely ready for analysis. The goal of this project was to take a famously messy dataset (the Google Play Store App data), engineer it into a clean mathematical state, and extract actionable business insights regarding app success, pricing, and sizing.

## 💡 Key Market Insights
* **The Most Saturated Market:** The **GAME** category dominates the Play Store with over **30 billion** total installs, making it the most competitive space for developers, followed closely by the Communication and Social categories.
* **The Size vs. Rating Myth:** Massive apps (over 60MB) actually tend to **maintain stable, higher ratings** (rarely dropping below 3.0) compared to lightweight apps (under 20MB), which show a massive variance and contain almost all of the 1-star and 2-star reviews. 
* **The Free vs. Paid Dynamic:** While Free apps capture the overwhelming majority of the total install volume, Paid apps tend to maintain a higher average user rating, likely due to higher development standards and the absence of intrusive ads.

## 🛠️ Data Engineering & Cleaning (The "Boss Fight")
Before any charts could be drawn, the dataset required heavy preprocessing to handle broken data types, missing values, and logical outliers.

* **Custom Feature Engineering:** The `Size` column contained mixed string formats (e.g., `15M`, `500k`, and `Varies with device`). I wrote a custom Python function to standardize all valid entries into uniform Megabyte (MB) floats and coerce invalid entries to null.
* **Regex String Manipulation:** Stripped non-numeric characters (`+`, `,`, `$`) from the `Installs` and `Price` columns to convert them from text objects into actionable integer/float types.
* **Outlier Eradication:** Hunted down and removed mathematical impossibilities, including a database glitch where an app was given a user rating of `19.0` (on a 1-5 scale).
* **Sanity Sweeps:** Handled nulls, dropped scraped duplicates, and verified the absence of negative pricing or negative install counts.

## 📈 Visualizations
The analysis includes Matplotlib visualizations to communicate findings:
1. **Bar Chart:** Top 10 Most Installed App Categories.
2. **Scatter Plot:** Analyzing the correlation between App Size (MB) and User Rating.

## 💻 Tech Stack
* **Language:** Python
* **Libraries:** Pandas, NumPy, Matplotlib
* **Environment:** Jupyter Notebook / VS Code Virtual Environment

---
*This project was built by me to demonstrate foundational Data Wrangling and EDA skills for Machine Learning preprocessing.*
