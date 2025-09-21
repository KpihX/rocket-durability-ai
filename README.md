# 🚀 Predictive Maintenance of NASA Turbofan Engines  
*Hi! PARIS DataBootcamp 2025 – Remaining Useful Life Prediction (Binary Classification)*  

---

## 🌍 Context  

Aircraft engines are critical components whose **failures can lead to catastrophic consequences**.  
Modern predictive maintenance leverages **sensor data** and **machine learning** to anticipate failures before they occur.  

The **NASA C-MAPSS dataset** provides multivariate time-series sensor measurements of turbofan engines across multiple lifecycles.  
Our goal in this project is to **predict whether an engine will fail within the next 30 cycles**.  

Instead of estimating the exact Remaining Useful Life (RUL), we recast the problem into a **binary classification task**:  

- **1 → At risk (failure in < 30 cycles)**  
- **0 → Safe (failure in ≥ 30 cycles)**  

This framing enables **faster decision-making** and provides an actionable failure alert mechanism.

---

## 🔎 Methodology  

Our approach followed a **scientific pipeline**:  

### 1️⃣ Data Cleaning & Preparation  
- Dropped irrelevant columns  
- Built the **binary target variable** from RUL values  
- Scaled features with **StandardScaler / MinMaxScaler**  
- Encoded categorical features with **OneHotEncoder / LabelEncoder**  
- Dealt with class imbalance using **class weighting**  

### 2️⃣ Data Exploration & Visualization  
- **Lifecycle analysis**: examined sensor degradation trends across time cycles  
- **Sensor variance study**: identified sensors with high predictive potential  
- **Correlation analysis**: revealed strong links between certain sensors (T50, HPC, LPC) and RUL  
- **Fleet-level degradation**: consistent patterns across multiple engines  

### 3️⃣ Machine Learning Models  
We benchmarked several classical ML algorithms:  
- Logistic Regression  
- K-Nearest Neighbors (K-NN)  
- Random Forest  
- Gradient Boosting  
- XGBoost  

**Metric prioritized:** Recall (catching failures is more important than overall accuracy).  

### 4️⃣ Deep Learning Model  
Implemented a **Neural Network** using TensorFlow/Keras:  
- Dense layers with ReLU activations  
- Binary cross-entropy loss  
- Adam optimizer  

### 5️⃣ Explainability  
We applied **SHAP (SHapley Additive exPlanations)** to tree-based models to:  
- Rank the most influential features  
- Understand feature contributions (positive/negative)  
- Provide transparency for predictive maintenance decisions  

---

## 📊 Results  

| Model                | Accuracy | Recall | F1-Score |
|----------------------|----------|--------|----------|
| Logistic Regression  | ~0.95    | ~0.40  | ~0.47    |
| K-NN (tuned)         | ~0.96    | ~0.43  | ~0.47    |
| Random Forest (tuned)| ~0.97    | **0.65** | ~0.55    |
| Gradient Boosting    | ~0.97    | ~0.45  | ~0.52    |
| XGBoost (tuned)      | ~0.97    | **0.73** | ~0.60    |
| Neural Network (DL)  | ~0.90    | Moderate | Moderate |

✅ **Best model:** Tuned **XGBoost** (Recall = 0.73)  
⚡ SHAP confirmed **sensor readings and time cycles** as key drivers of failure prediction.  

---

## 🧪 Scientific Justification  

- **Binary classification** was chosen over regression because it aligns better with the operational goal:  
  *“Will the engine fail soon, yes or no?”*  
- **Recall maximization** ensures fewer **false negatives** (missed failures).  
- **Hyperparameter tuning (GridSearchCV)** improved recall significantly, especially for ensemble methods.  
- **Explainability (SHAP)** increases trust in models by showing which sensors drive predictions.  

---

## 🔮 Conclusion  

This project demonstrates that **predictive maintenance with ML/DL** is a powerful tool to reduce operational risks.  
By combining:  
- **Rigorous preprocessing**  
- **Explainable machine learning**  
- **Deep learning models**  

We can **anticipate engine failures** with strong reliability, paving the way for **safer aviation and cost-effective maintenance planning**.  

---

## 👨‍👩‍👧‍👦 Contributors  

**Name:** KAMDEM Ivann  
**School:** École Polytechnique  
**Track:** Intermediate  

**Name:** WU Jinyang  
**School:** École Polytechnique  
**Track:** Beginner  

**Name:** Montandon Tanguy  
**School:** HEC Paris  
**Track:** Beginner  

**Name:** Moubareckou Mohamed  
**School:** École Polytechnique  
**Track:** Beginner  

**Name:** Picq Pierre  
**School:** HEC Paris  
**Track:** Beginner  

**Name:** Blackwell-Hunt Derrick  
**School:** HEC Paris  
**Track:** Intermediate  

**Name:** Civilo Yigit  
**School:** HEC Paris  
**Track:** Intermediate  

---

## 📚 Additional Resources  

For those who want to **go deeper** and explore the background material from the camp:  

- 🔗 [HI AI Camp Resources](https://drive.google.com/drive/folders/1ddIPqaRcs80SLb8CdXedkpDn86X3mFDa?usp=sharing)  
  *(contains the datasets required to run the notebooks in this project)*  

- 🔗 [HI AI Camp Other Resources](https://drive.google.com/drive/folders/1BJAklj_Abvr3vEAkdfSwWRvg1tuTU3oy)  

---

📌 *Hi! PARIS DataBootcamp 2025 – NASA Turbofan Project*
