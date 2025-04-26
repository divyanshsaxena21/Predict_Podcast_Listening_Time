# 🎧 Predicting Podcast Listening Time  
**Kaggle Playground Series – Season 5 Episode 4 (April 2025)**  

Welcome to the **2025 Kaggle Playground Series!** This lightweight competition challenges participants to predict how long users will listen to podcast episodes, using metadata like episode length, sentiment, guest popularity, and more. It's a fun and practical task designed to hone your machine learning skills with a real-world twist.

---

## 🚀 Challenge Overview

📌 **Objective**: Predict the **Listening Time (in minutes)** for each podcast episode.

📊 **Evaluation Metric**:  
Submissions are scored using **Root Mean Squared Error (RMSE)**.

\[
\text{RMSE} = \sqrt{ \frac{1}{N} \sum_{i=1}^{N} (y_i - \hat{y}_i)^2 }
\]

🗓️ **Competition Dates**:
- **Start**: April 1, 2025  
- **End**: April 30, 2025, 11:59 PM UTC  

🔗 [View Competition on Kaggle](https://www.kaggle.com/competitions/playground-series-s5e4)

---

## 🧾 Dataset Summary

📦 **Total Rows**: 750,000  
📄 **Columns**: 12 (11 Features + 1 Target)  

### 🧩 Features

| Column                       | Description                                          |
|-----------------------------|------------------------------------------------------|
| `id`                        | Unique identifier for each podcast entry             |
| `Podcast_Name`              | Name of the podcast                                  |
| `Episode_Title`             | Title of the episode                                 |
| `Episode_Length_minutes`    | Duration of the episode in minutes                   |
| `Genre`                     | Genre of the podcast                                 |
| `Host_Popularity_percentage`| Popularity score of the host                         |
| `Publication_Day`           | Day of the week episode was released                 |
| `Publication_Time`          | Time of day episode was published                    |
| `Guest_Popularity_percentage`| Guest's popularity score (if any)                  |
| `Number_of_Ads`             | Number of ads in the episode                         |
| `Episode_Sentiment`         | Sentiment of the episode title/description           |
| `Listening_Time_minutes`    | **Target variable**: time spent listening (minutes)  |

💡 Note: The dataset includes missing values (e.g., `Episode_Length_minutes`, `Guest_Popularity_percentage`) and mixed data types.

---

## 🧠 Model Training

### ✅ Final Model: **LightGBM Regressor**

LightGBM was selected for its:
- High performance on large tabular data
- Ability to handle missing values
- Fast training and inference

```python
import lightgbm as lgb

lgbm_model = lgb.LGBMRegressor(n_estimators=100, random_state=42)
lgbm_model.fit(X_train, y_train)
```

---

## 📊 Model Performance

🧪 **Evaluation on Train Set**:

| Metric         | Value      |
|----------------|------------|
| **R² Score**   | 0.7735     |
| **RMSE**       | 12.9183    |
| **MAE**        | 9.4292     |
| **MSE**        | 166.8827   |

---

## 📤 Submission Format

Submissions must be in CSV format and follow this structure:

```
id,Listening_Time_minutes
750000,45.437
750001,44.120
750002,41.984
...
```

- **Column 1**: `id` (from test set)  
- **Column 2**: `Listening_Time_minutes` (predicted)

---

## 📚 About the Playground Series

The **Kaggle Tabular Playground Series** is a collection of short-term, synthetic-data challenges designed for:
- Practicing model development and feature engineering  
- Testing new ML libraries and techniques  
- Competing in a low-pressure, high-learning environment

These datasets are synthetically generated but based on real-world structures to encourage meaningful experimentation.

---

## 🧬 Why Synthetic Data?

✅ No leakage from public labels  
✅ More creative feature design possibilities  
✅ Encourages fair competition  
✅ Closer alignment with real-world feature semantics

---

## 📢 Citation

> Walter Reade and Elizabeth Park.  
> *Predict Podcast Listening Time*, Kaggle, 2025  
> [Competition Link](https://www.kaggle.com/competitions/playground-series-s5e4)

---

## 🧰 Tools Used

- **Python**
- **Pandas / NumPy**
- **LightGBM**
- **Scikit-learn**

---

## 🏁 Final Thoughts

This competition was a great playground to:
- Handle missing data
- Engineer features from timestamps
- Explore categorical encodings
- Balance bias vs. variance in regression

📈 Looking ahead, ensemble methods and deeper NLP insights into titles/sentiment could further improve predictions.
