# **CDC Diabetes Health Indicators Project**

## **Introduction and Data Understanding**
The goal of this project is to predict diabetes occurrence using a dataset of health indicators provided by the CDC. The main objective is to identify key factors that influence diabetes prevalence and develop a predictive model for early detection and prevention. By leveraging machine learning techniques, we aim to create a robust model that can accurately predict diabetes risk and provide actionable insights for public health interventions.

**Dataset:** Includes health indicators such as BMI, physical activity levels, cholesterol levels, and demographic and lifestyle factors.  
**Target Variable:** `diabetes_binary` (1 = Diabetic, 0 = Non-Diabetic).

![Introduction Image]("C:\Users\USER\Pictures\images.jpeg")

---

## **Data Cleaning and Feature Engineering**
### **Imputation Techniques:**
- **Continuous Variables:** Applied mean/median imputation using `SimpleImputer` from `sklearn.impute` for variables like BMI and Age.
- **Categorical Variables:** Used mode imputation for categorical features like Sex and Education.

### **Feature Engineering:**
- **BMI Categories:** Transformed BMI values into categorical bins (e.g., Underweight, Normal weight, Overweight, Obese) using `pd.cut()` for more meaningful insights.
- **Age Binning:** Grouped ages into predefined bins (e.g., 0-18, 19-35, 36-50, 51-65, 66+) to improve model performance.

### **Bivariate Analysis:**
- **Cross-tabulation:** Explored the relationship between `diabetes_binary` and features like HighBP, HighChol, and PhysActivity.
- **Correlation Matrix:** Computed correlations to understand relationships between `diabetes_binary` and continuous features like BMI, Age, and Income.
- **Visualizations:** Used bar plots, point plots, and violin plots to represent associations between the target variable and other features.

![Data Cleaning Image](https://miro.medium.com/max/1400/1*VZ2iO1vS6ILgniUOePN2MQ.png)

---

## **Data Balancing**
### **Techniques Applied:**
- **SMOTE (Synthetic Minority Over-sampling Technique):** Generated new samples for the minority class by interpolating between existing samples.
- **NearMiss:** Reduced the majority class by selecting the closest samples to the minority samples.
- **SMOTETomek:** Combined oversampling and undersampling techniques to achieve a balanced dataset by removing Tomek links.

### **Normalization:**
Standardized continuous features using `StandardScaler` to scale features to have zero mean and unit variance.

---

## **Exploratory Data Analysis (EDA)**
### **Key Observations:**
- **BMI and General Health:** High BMI is significantly associated with poor general health. Older populations are more prone to obesity-related health issues.
- **Income and Age:** Older individuals generally have lower income levels, which may influence health outcomes.
- **Physical Inactivity:** A strong predictor of diabetes.
- **High Blood Pressure and Cholesterol:** Prevalent among diabetic individuals, indicating the need for integrated healthcare approaches.
- **Smoking Habits:** More common among those with diabetes, highlighting the need for smoking cessation programs.
- **Mental Health:** Slight association between poor general health and mental health issues.
- **Healthcare Access:** Limited access is more common among lower-income and older individuals, potentially contributing to higher diabetes rates.

![EDA Image](https://upload.wikimedia.org/wikipedia/commons/thumb/1/1b/Diabetes_mellitus_world_map_-_DALY_-_WHO2004.svg/800px-Diabetes_mellitus_world_map_-_DALY_-_WHO2004.svg.png)

---

## **Model Training and Evaluation**
### **Models Trained:**
- Logistic Regression
- Decision Trees
- Random Forests
- Gradient Boosting

### **Evaluation Metrics:**
- **AUC Score**
- **Accuracy**
- **Precision**
- **Recall**
- **F-measure**

### **Best Performing Model:**
- **Random Forest:** Demonstrated the best performance, particularly in terms of the AUC score.

### **Hyperparameter Tuning:**
Conducted using grid search, which improved the model’s accuracy, precision, recall, and F-measure.

![Model Training Image](https://scikit-learn.org/stable/_static/ml_map.png)

---

## **Model Deployment**
### **Platform:** Streamlit
### **Steps Involved:**
- **Model Preparation:** Pre-trained Random Forest classifier saved as a pickle file.
- **User Interface Design:** Interactive widgets for inputting health data.
- **Input Data Processing:** User inputs converted into binary and numerical values. BMI and Health Score calculated based on input data.
- **Prediction Generation:** Probabilities of being Diabetic, Pre-Diabetic, or Non-Diabetic presented in percentages.
- **Result Display:** Detailed explanations of BMI and Health Score provided.

![Deployment Image](https://docs.streamlit.io/0.89.0/en/_images/streamlit-logo-primary-colormark-darktext.png)

---

## **Limitations**
### **Data Limitations:**
- **Quality and Completeness:** The dataset may have missing or inaccurate data.
- **Generalizability:** Limited to a specific population, reducing applicability to other groups.

### **Model Limitations:**
- **Complexity:** Random Forest is robust but complex, making feature importance difficult to interpret.

### **Technical Limitations:**
- **Local Deployment:** Limits accessibility to a wider audience.

### **User Experience:**
- **Manual Input:** Data collection can be time-consuming and prone to errors.
- **Interpretation of Results:** Some users may find it challenging to understand their health metrics and risk levels.

![Limitations Image](https://miro.medium.com/max/1838/1*7IPd6QbPtp62zobW_KyDOQ.png)

---

## **Conclusions**
- **Model Performance:** Random Forest demonstrated strong performance in predicting diabetes risk.
- **User Engagement:** The Streamlit application provided an interactive and user-friendly platform.
- **Health Insights:** The application provided valuable health insights, aiding users in understanding their health status.

### **Key Recommendations:**
- **Improve Lifestyle Factors:** Focus on reducing physical inactivity and managing BMI.
- **Community Engagement:** Educate communities and collaborate with healthcare providers.


---

## **Next Steps**
### **Improving Model Interpretability and Performance:**
- **Regular Model Updates:** Periodically retrain the model with new data.
- **Technical Enhancements:** Deploy the application on a cloud platform to enhance accessibility and scalability.

### **User Experience Improvements:**
- **Automated Data Entry:** Integrate with wearable devices and health apps for automatic data input.
- **Educational Resources:** Provide users with resources to interpret their results and take preventive measures.
