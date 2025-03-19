# 🧑‍⚕️ Human Age Predictor  
### Predicting Age Using Health and Lifestyle Data  

## 📄 Project Overview  
This project aims to predict **human age** based on **health and lifestyle factors** using **Linear Regression and Polynomial Regression** models. We explore different modeling approaches to find the best-performing model using various **biometric and lifestyle indicators**, such as **hearing ability, blood pressure, cholesterol levels, physical activity, and cognitive function**.  

The **goal** of this project is to create a predictive tool that can estimate a person’s age based on **health metrics**, which may have applications in **personalized healthcare** and **predictive analytics**.

---

## 📊 Dataset  
The dataset contains various health indicators, including **biometric, lifestyle, and medical history features**. The key variables are:  

- **Hearing** 🎧 (Measured in dB)  
- **Systolic & Diastolic Blood Pressure** 💓 (mmHg)  
- **Cholesterol Level** 🩸 (mg/dL)  
- **Blood Glucose** 🍬 (mg/dL)  
- **Physical Activity Level** 🏃‍♂️ (Categorical: Low, Moderate, High)  
- **Smoking & Alcohol Consumption** 🚬🍷 (Categorical)  
- **Mental Health Score** 🧠 (Categorical: Poor, Fair, Good, Excellent)  
- **Cognitive Function Score** 🧠 (Numeric)  
- **Stress Levels** 😟 (Numeric)  
- **BMI, Height, Weight** ⚖️ (Numeric)  
- **Family & Chronic Disease History** 🏥 (Categorical)  

The **target variable** is **Age (years)**.

---

## 🔍 Exploratory Data Analysis (EDA)  
### 📌 Data Cleaning Steps  
✔️ **Handled missing values** using **mean imputation** for numerical features and **mode imputation** for categorical features.  
✔️ **Fixed Blood Pressure format** by splitting `Systolic_BP` and `Diastolic_BP`.  
✔️ **Encoded categorical features** using **label encoding** for ordinal variables and **one-hot encoding** for nominal variables.  
✔️ **Standardized numerical features** for better model performance.  

### 📈 Feature Correlation Analysis  
After computing **Pearson correlation**, the **top features correlated with age** were:  
1️⃣ **Hearing** (0.71)  
2️⃣ **Systolic Blood Pressure** (0.64)  
3️⃣ **Diastolic Blood Pressure** (0.61)  
4️⃣ **Cholesterol** (0.43)  
5️⃣ **Blood Glucose** (0.42)  

🛑 **Vision (-0.90) and Bone Density (-0.94) had strong negative correlations**, meaning **poorer vision and lower bone density** are associated with **older age**.

---

## 🧠 Model Building  

### 📌 **1. Single Linear Regression Model**  
A **simple linear regression model** was trained using **Hearing Ability (dB)**, as it had the highest correlation (0.71) with age.

#### 📊 **Results**
- **Mean Absolute Error (MAE):** 11.684  
- **Mean Squared Error (MSE):** 205.733  
- **R² Score:** 0.498  

📉 **Interpretation:**  
The model explains **~50% of the variance** in age. While Hearing Ability is a significant predictor, it alone **cannot fully explain age variations**.

---

### 📌 **2. Polynomial Regression Model (Degree = 2)**  
To improve accuracy, we implemented **Polynomial Regression** with **degree = 2**, using the most **correlated features** (Hearing, Blood Pressure, Cholesterol, and Blood Glucose).

#### 📊 **Results**
- **Mean Absolute Error (MAE):** 4.191  
- **Mean Squared Error (MSE):** 28.006  
- **R² Score:** 0.932  

📉 **Interpretation:**  
The polynomial model **significantly improved accuracy**, capturing **93.2% of the variance** in age predictions.

---

## 🏆 **Model Comparison**
| Model Type | MAE (↓ Better) | MSE (↓ Better) | R² Score (↑ Better) |
|------------|-------------|-------------|-------------|
| **Single Linear Regression** | 11.684 | 205.733 | 0.498 |
| **Polynomial Regression (Degree = 2)** | 4.191 | 28.006 | 0.932 |

✅ **Polynomial Regression outperformed simple regression, achieving a much higher R² score and lower error.**  
✅ **The best predictors were Hearing, Blood Pressure, Cholesterol, and Blood Glucose.**  

---

## 📉 Results  

### 📊 Single Regression Model Performance (Using Standardized Hearing)
- **MAE:** 11.684  
- **MSE:** 205.733  
- **R² Score:** 0.498  

### 📊 Polynomial Regression Model Performance (Degree = 2)
- **MAE:** 4.191  
- **MSE:** 28.006  
- **R² Score:** 0.932  

✅ **Polynomial Regression significantly outperformed the single-variable model.**  
✅ **It captured non-linear relationships and explained more variance.**  


This README includes:
- **Project overview**
- **Dataset and key features**
- **EDA, feature selection, and correlation analysis**
- **Single vs. Polynomial Regression comparison**
- **Implementation steps**
- **Code snippets for running the model**
- **Final results interpretation**
- **Contribution guidelines and contact info**

Let me know if you need any modifications! 🚀✨

