# 📊 Exploratory Data Analysis (EDA) – Complete Guide  

## 📖 What is EDA?  
Exploratory Data Analysis (EDA) is the process of analyzing datasets to summarize their main characteristics using:  

- 📈 **Statistics**  
- 📊 **Visualization**  
- 🧹 **Data Cleaning**  

It helps in:  
- 🔍 Detecting patterns  
- ⚠️ Spotting anomalies  
- ✅ Testing assumptions  
- 🤖 Preparing data for machine learning models  

---
# ⚖️ Normalization (Min-Max Scaling)

## 🔹 What it is
Normalization (also called **Min-Max Scaling**) is a feature scaling technique used to bring all numerical features to a **common scale**, usually between **0 and 1**.  
This ensures that no feature dominates due to its range.

---

## 🔹 Why it is important
Normalization is important for algorithms that are sensitive to the scale of data, such as:  

- **K-Nearest Neighbors (KNN)**  
- **Neural Networks**  
- **Gradient descent-based models**  

---

## 🔹 Formula
The formula for Min-Max scaling is:  

\[
X_{norm} = \frac{X - X_{min}}{X_{max} - X_{min}}
\]

Where:  
- \(X\) = original value  
- \(X_{min}\) = minimum value in the feature  
- \(X_{max}\) = maximum value in the feature  
- \(X_{norm}\) = normalized value (between 0 and 1)  

---

## 🔹 Example with Formula Applied

Suppose we have a feature **Age**:

| Age |
|-----|
| 20  |
| 30  |
| 40  |
| 60  |

1. Identify minimum and maximum:  
   - \(X_{min} = 20\)  
   - \(X_{max} = 60\)  

2. Apply the formula for each value:

\[
X_{norm} = \frac{X - X_{min}}{X_{max} - X_{min}}
\]

- For 20: \( (20-20)/(60-20) = 0/40 = 0 \)  
- For 30: \( (30-20)/(60-20) = 10/40 = 0.25 \)  
- For 40: \( (40-20)/(60-20) = 20/40 = 0.5 \)  
- For 60: \( (60-20)/(60-20) = 40/40 = 1 \)  

**Normalized Ages:** `[0, 0.25, 0.5, 1]`
---
