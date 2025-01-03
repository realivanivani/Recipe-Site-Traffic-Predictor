![image](https://github.com/user-attachments/assets/a0e18834-efb2-4daa-9a36-039963e84f94)# Recipe Traffic Prediction for Tasty Bytes

## Project Background
As a data scientist for Tasty Bytes, I was tasked with developing a predictive model to identify recipes likely to generate high site traffic. Tasty Bytes, a subscription-based recipe discovery platform, has observed up to a 40% increase in website traffic when a popular recipe is featured on the homepage. The challenge was to replace the subjective selection of homepage recipes with a data-driven approach, aiming for a prediction accuracy of at least 80% for identifying high-traffic recipes.

This project utilized recipe data, including attributes such as calories, macronutrients, servings, and historical traffic outcomes. A key step was analyzing the relationships between these features to uncover insights and build a predictive model for optimizing recipe selection.

---

## Executive Summary
This report outlines the findings from analyzing Tasty Bytes recipe data and building a predictive model for homepage recipe selection. Key insights include:
- **Correlations with High Traffic:** High-traffic recipes showed a positive correlation with recipe category and a moderate negative correlation with calories per servings.
- **Model Performance:** A Logistical regression model achieved 81% accuracy in predicting high-traffic recipes.
- **Operational Impact:** Recommendations focus on refining recipe selection and tracking performance metrics to enhance user engagement.
  
These findings enable actionable strategies to improve site performance as requested.
Few questions regarding the data remain to further improve the model.

---

## Insights Deep-Dive

### Data Validation & Cleaning
- **Validation:** All columns were verified for consistency and completeness.
- **Cleaning Steps:**
  - Imputed missing values in numerical columns with medians.
  - Normalized recipe categories to ensure consistent grouping.
  - Identified and resolved outliers using interquartile ranges.

### Exploratory Analysis
- **Validation:**
    -  All columns were verified for consistency and completeness.
- **Cleaning:**
    -  Normalized recipe categories to ensure consistent grouping (Chicken and Chicken Breast merged).
  	-  Servings column converted to numerical and cleaned
- **Outliers/Missing data:**
    -  There were 52 missing nutritional values (calories, carbs, sugar, proteins). I tried to imputed missing values with medians per category, but then model performed worst.
    -  Outliers for calories columns: 11 recipes with calories per serving > 1500cal) and 27 recipes with < 5 calories that are not Beverages
    -  I tried to remove outliers but again the model performed worst.

<img width="480" alt="image" src="https://github.com/user-attachments/assets/c43cbc38-613c-47fa-a0b6-e7689c20ee29" />

- **Correlation Analysis:**
  - A heatmap of feature correlations revealed:
    - A strong negative correlation (-0.88) between **category** and high traffic.
    - A moderate negative correlation (-0.57) between **calories per serving** and high traffic.
    - A slight negative correlation (-0.41) between **carbohydrates per serving** and high traffic.
- **Insights from Correlation Heatmap:**
    - Three categories have more than 90% of recipes with high traffic.
    - Recipes lower in calories are more likely to attract traffic.

<img width="492" alt="image" src="https://github.com/user-attachments/assets/5f3b6879-a8bf-46b8-a2a5-59c5107ed149" />

### Model Development
- **Problem Definition:** A classification problem to predict whether a recipe will generate high traffic.
- **Baseline Model:** A Logistic Regression model achieved 81% accuracy.
- **Comparison Model:** A random forest model achieved lower accuracy at 78%, with a better F1 score of 80%.


### Model Evaluation
- **Performance Metrics:**
  -  Logistic Regression:
        Precision: 81%
        Recall: 79%
        F1 Score: 79%
  -  Random Forest:
        Precision: 78%
        Recall: 82%
        F1 Score: 80%

**Conclusion**
- Logical regression model performed with 81% precision, meaning that the model will accurately predict a recipe with a High traffic 81% of times, which is higher than requested limit of 80%.
- Random Forest had 78% precision for High, but it had a higher Recall, meaning that it better identified all truly popular recipes.

---

## Recommendations
1. **Deploy the Linear Regression Model:** This model is as accurate as requested to identify high-traffic recipes with 80% of time.
2. **Expand Feature Set:** Consider incorporating additional information, like prep time, cost, ingrediencies or picture analysis, or even user interaction data (e.g., click-through rate, time spent on recipe pages) to further refine the model’s predictions, enhancing its precision and recall.
3. **Further data cleaning if needed:** With additional information, we can clean the data better especially for calories and servings.
4. **Periodic Model Re-Evaluation:** Reassess model performance periodically using updated data to ensure it continues to align with evolving user preferences.
---

For further details, refer to the accompanying notebook, which includes code, visualizations, and step-by-step analysis.
