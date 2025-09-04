# Titanic Pandas Assignment

_Note: You must actively explore the pandas library and apply its functions to implement and solve each of the given questions._

**Dataset:** _Titanic — Machine Learning from Disaster_ (download `train.csv` and `test.csv` from the Kaggle competition page). ([Kaggle](https://www.kaggle.com/competitions/titanic))

The `train.csv` file contains 891 passenger records and the usual Titanic feature set (PassengerId, Survived, Pclass, Name, Gender, Age, SibSp, Parch, Ticket, Fare, Cabin, Embarked).

---

## Objective

Use **pandas** to explore, clean, transform, and analyze the Titanic dataset. Rather than model building, the assignment focuses on real-world data tasks (missing values, grouping, pivot tables, joins, feature engineering).

---

## Setup / Submission

1. Download `train.csv` and `test.csv` from the Kaggle Titanic competition page. ([Kaggle](https://www.kaggle.com/competitions/titanic?utm_source=chatgpt.com))
2. Create a Jupyter notebook named `titanic_pandas_assignment.ipynb`. Put each task in a clearly labeled cell and show code + output.
3. Submit: the notebook, any exported CSVs you created (e.g., `train_cleaned.csv`), and a short `README.md` describing how you approached the tasks.
4. (Optional) If you use the Kaggle API to download data in code, include the code snippet (but do not include your Kaggle API key in submissions).

---

## Tasks

### Part A — Basic

1. **Load & Inspect**
   - Load `train.csv` into a DataFrame `df`. Show `df.shape`, `df.info()`, and `df.head(5)`.
2. **Column summary**
   - Produce a summary table listing: `column name`, `dtype`, `# missing`, `# unique values`. Sort it by `# missing` descending.
3. **Value counts & proportions**
   - For `Pclass`, `Gender`, and `Embarked`, show value counts and percentages (as a DataFrame).
4. **Select & filter**
   - Create a DataFrame `female_firstclass_over_30` containing female passengers in 1st class older than 30. Show the top 10 rows sorted by `Fare` desc.
5. **Basic aggregations**
   - Compute: mean/median/mode of `Age` (ignore missing), mean `Fare` per `Pclass`, survival rate (mean of `Survived`) overall and by `Gender`.

### Part B — Intermediate

1. **Missing value imputation**
   - Impute missing `Age` values using median age grouped by `Pclass` and `Gender` (e.g., fill `Age` with the median age of people in the same `Pclass` and `Gender`). Create a new column `Age_imputed`. Show before/after missing counts.
2. **Feature extraction from text**
   - Extract `Title` (e.g., Mr, Mrs, Miss, Master, etc.) from the `Name` column into a new column `Title`. Show the counts for each title.
3. **Family size & new feature**
   - Create `FamilySize = SibSp + Parch + 1`. Create `IsAlone` boolean (True if FamilySize==1). Show survival rate by `IsAlone`.
4. **Pivot table and multi-index groupby**
   - Produce a pivot table showing survival rate indexed by `Pclass` (rows) and `Gender` (columns). Then produce a groupby that shows average `Fare` and `Age_imputed` for `Pclass, Embarked`.
5. **String cleaning & parsing**
   - Clean `Cabin` column: replace missing cabins with `'Unknown'`. Extract cabin letter (first character of cabin string) into `CabinDeck` (if multiple cabins listed, take first). Show survival rate by `CabinDeck`.

### Part C — Advanced

1. **Advanced joins / merges**
   - Create a small lookup DataFrame `ticket_counts` with `Ticket` and how many times that ticket appears (ticket frequency). Merge this back into `df` as `TicketCount`. Show top 10 tickets by `TicketCount`.
2. **Outlier detection & handling**
   - Identify passengers with `Fare` in the top 1% (by value). Create a flag column `Fare_outlier`. Replace those `Fare` values with the 99th percentile value and show the effect on mean/median Fare.
3. **Complex aggregation with apply**
   - Write a function that categorizes age groups: `Child` (<12), `Teen` (12–17), `YoungAdult` (18–30), `Adult` (31–60), `Senior` (>60). Use `.apply` or `pd.cut` to create `AgeGroup`. Show survival rate for each `AgeGroup` by `Gender`.
4. **Multi-step pipeline**
   - Build a small preprocessing pipeline (in the notebook) that:
     - fills missing `Embarked` with the mode,
     - imputes `Age` using the `Pclass`+`Gender` median rule (from task 6),
     - encodes `Gender` to numeric (0/1),
     - drops unused columns (`Name`, `Ticket`, `Cabin`),
     - outputs the cleaned DataFrame `df_clean`.
   - Show `df_clean.head()` and `df_clean.info()`.
5. **Challenge analysis / storytelling**
   - Answer (in markdown + code) the question: _"Which combination of features (choose at most 3 features) seems most associated with survival? Use groupby/agg/pivot tables to justify your claim and show the supporting tables/plots."_ Provide one short paragraph summarizing your findings.

---

## Deliverable checklist

- `titanic_pandas_assignment.ipynb` with labeled cells for each task.
- `train_cleaned.csv` (if created).
- `README.md` (one paragraph about your approach, any assumptions/choices).

---
