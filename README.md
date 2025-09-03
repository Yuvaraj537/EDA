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

# Feature Scaling

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
# StandardScaler in Machine Learning

## 🔹 What is StandardScaler?

`StandardScaler` standardizes the features by removing the mean and scaling to unit variance. After scaling:

- **Mean** = 0  
- **Standard Deviation** = 1  

> ⚠️ This is different from `MinMaxScaler`, which scales data to a fixed range, usually [0,1].

---

## 🔹 Formula

\[
X_{\text{scaled}} = \frac{X - \mu}{\sigma}
\]

Where:  
- \(X\) = original value  
- \(\mu\) = mean of the data  
- \(\sigma\) = standard deviation of the data  

---

## 🔹 Step-by-Step Example

### Original Data
### Step 1: Calculate the Mean (\(\mu\))
\[
\mu = \frac{2 + 3 + 5 + 6 + 6}{5} = 4.4
\]

### Step 2: Calculate the Standard Deviation (\(\sigma\))
\[
\sigma = \sqrt{\frac{(2-4.4)^2 + (3-4.4)^2 + (5-4.4)^2 + (6-4.4)^2 + (6-4.4)^2}{5}}
\]

\[
\sigma \approx 1.6248
\]

### Step 3: Standardize Each Value
\[
Z = \frac{X - \mu}{\sigma}
\]

| Original \(X\) | Standardized \(Z\) |
|----------------|------------------|
| 2              | -1.477           |
| 3              | -0.862           |
| 5              | 0.369            |
| 6              | 0.985            |
| 6              | 0.985            |

### Step 4: Final Output
[[-1.4770999 ]
[-0.86164044]
[ 0.36944548]
[ 0.98485496]
[ 0.98485496]]

----

## 🔹 Summary

| Scaler          | Range / Centering |
|-----------------|-----------------|
| MinMaxScaler    | Scales values to [0,1] |
| StandardScaler  | Centers data around 0 with standard deviation 1 |

---

## 🔹 When to Use

Use `StandardScaler` when you want your features to have **similar scale** and be **centered around 0**.  
This is important for algorithms like:  

- Support Vector Machines (SVM)  
- K-Nearest Neighbors (KNN)  
- Logistic Regression  
- Neural Networks  

---

# 📌 Types of Data

In statistics and machine learning, data can be broadly classified into **Qualitative (Categorical)** and **Quantitative (Numerical)** data.  

---

## 1️⃣ Qualitative (Categorical) Data
Data that describes **qualities or categories**. Usually not numeric, though sometimes represented with numbers.  

### 🔹 Nominal
- **Definition:** Categories **without any order**.  
- **Examples:**  
  - Gender: Male, Female  
  - Colors: Red, Blue, Green  
  - Blood Group: A, B, AB, O  

### 🔹 Ordinal
- **Definition:** Categories **with a meaningful order**, but differences between them are not numeric.  
- **Examples:**  
  - Rating: Low, Medium, High  
  - Education Level: High School < Bachelor < Master < PhD  
  - Satisfaction: Unsatisfied < Neutral < Satisfied  

---

## 2️⃣ Quantitative (Numerical) Data
Data that can be **measured or counted** and is numeric.  

### 🔹 Discrete
- **Definition:** Countable values, often integers.  
- **Examples:**  
  - Number of students in a class: 25, 30, 40  
  - Number of cars in a parking lot: 10, 12, 15  
  - Number of goals in a football match: 0, 1, 2  

### 🔹 Continuous
- **Definition:** Measurable values that can take **any value within a range**, including decimals.  
- **Examples:**  
  - Height of students: 150.5 cm, 172.3 cm  
  - Weight of objects: 60.2 kg, 75.5 kg  
  - Temperature: 36.6°C, 37.8°C  

---

## ✅ Summary Table

| Type          | Subtype    | Example                                 |
|---------------|------------|-----------------------------------------|
| Qualitative   | Nominal    | Gender, Colors, Blood Group             |
| Qualitative   | Ordinal    | Rating, Education Level, Satisfaction   |
| Quantitative  | Discrete   | No. of students, Goals, Cars            |
| Quantitative  | Continuous | Height, Weight, Temperature             |



---

# 4️⃣ Data Visualization

Data visualization helps to **understand patterns, trends, and relationships** in your data.  
It can be categorized based on the number of variables analyzed.

---

## 📊 1. Univariate Analysis
- **Definition:** Analyzing **one variable** at a time to understand its **distribution, frequency, or proportion**.  
- **Common Plots:**  
  - **Histogram:** Shows the frequency distribution of numerical data  
  - **Bar Plot:** Displays categorical data counts  
  - **Pie Chart:** Shows proportion of categories  

**Example:**  
- Dataset: Student grades in a class  
- Visualization: Histogram to show how many students scored in each grade range  

---

## 📉 2. Bivariate Analysis
- **Definition:** Analyzing the **relationship between two variables**.  
- **Common Plots:**  
  - **Scatter Plot:** Shows correlation between two numerical variables  
  - **Correlation Heatmap:** Shows pairwise correlation values between variables  

**Example:**  
- Dataset: Study hours vs Exam scores  
- Visualization: Scatter plot to check if more study hours lead to higher scores  

---

## 📈 3. Multivariate Analysis
- **Definition:** Analyzing **three or more variables** to identify patterns, interactions, or outliers.  
- **Common Plots:**  
  - **Pair Plot:** Visualizes pairwise relationships among multiple numerical variables  
  - **Box Plot:** Shows distribution and outliers of a numerical variable across categories  

**Example:**  
- Dataset: Students’ study hours, sleep hours, and exam scores  
- Visualization: Pair plot to see how all three variables relate to each other  

---

## ✅ Summary Table

| Analysis Type       | Purpose                              | Plots/Charts                                | Example |
|--------------------|--------------------------------------|--------------------------------------------|---------|
| Univariate          | Single variable distribution        | Histogram, Bar Plot, Pie Chart             | Student grades histogram |
| Bivariate           | Relationship between 2 variables    | Scatter Plot, Correlation Heatmap          | Study hours vs Exam scores |
| Multivariate        | Interaction among 3+ variables      | Pair Plot, Box Plot                         | Study hours, Sleep, Exam scores |

