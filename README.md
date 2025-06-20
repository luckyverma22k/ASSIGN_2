# 🔌 Power System Load Type Prediction

This project aims to develop a machine learning model that predicts the **Load Type** (i.e., `Light_Load`, `Medium_Load`, or `Maximum_Load`) of a power system using historical data.

---

## 📌 Objective

The primary goal is to build a **classification model** capable of accurately predicting the load type based on power usage and other electrical indicators. This includes:

- Data cleaning and preprocessing
- Feature engineering (time-based)
- Model training and evaluation
- Time-aware validation strategy

---

## 🧠 Problem Overview

Each row in the dataset represents a snapshot of power system metrics collected on the first day of each month. The target variable is `Load_Type`, and the task is to classify the system into one of the three categories:

- `Light_Load`
- `Medium_Load`
- `Maximum_Load`

---

## 📁 Dataset Description

| Feature Name                        | Description                                  |
|------------------------------------|----------------------------------------------|
| `Date_Time`                        | Timestamp (first of the month)               |
| `Usage_kWh`                        | Energy consumption in kilowatt-hours         |
| `Lagging_Current_Reactive.Power_kVarh` | Reactive power drawn (lagging)         |
| `Leading_Current_Reactive_Power_kVarh` | Reactive power supplied (leading)     |
| `CO2(tCO2)`                        | CO2 emissions in parts per million (ppm)     |
| `Lagging_Current_Power_Factor`     | Power factor when load is inductive          |
| `Leading_Current_Power_Factor`     | Power factor when load is capacitive         |
| `NSM`                              | Number of seconds since midnight             |
| `Load_Type`                        | Target: Light, Medium, or Maximum Load       |

---

## 🛠️ Tech Stack

- Python
- Pandas, NumPy
- Scikit-learn
- Seaborn & Matplotlib (for visualization)
- Google Colab (runtime environment)

---

## ✅ Key Steps in the Notebook

1. **File Upload & Data Loading**  
   Uses Google Colab's `files.upload()` to import the dataset.

2. **Preprocessing**
   - Strips column names
   - Converts `Date_Time` to datetime
   - Drops invalid entries
   - Sorts data chronologically

3. **Feature Engineering**
   - Extracts `Month` and `Day` from `Date_Time`
   - Drops original `Date_Time` column

4. **Encoding**
   - Encodes the `Load_Type` column using `LabelEncoder`

5. **Train/Test Split**
   - Trains on all months except the **last month**
   - Tests on **last month** data to simulate real-world unseen prediction

6. **Model Training**
   - Uses `RandomForestClassifier` for classification

7. **Evaluation**
   - Prints classification report: accuracy, precision, recall, F1-score
   - Displays confusion matrix using Seaborn heatmap

---

## 📊 Model Evaluation

The model is evaluated on the test set (last month of data) using:

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix

These metrics provide a complete picture of the model’s performance across all load types.

---

## 📂 How to Run

1. Open the notebook in **Google Colab**.
2. Upload the `load_data.csv` file when prompted.
3. Run all cells sequentially.
4. View the prediction results and evaluation metrics.

---





