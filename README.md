# Recipe Traffic Prediction for Tasty Bytes

## Project Background
As a data scientist for Tasty Bytes, I was tasked with developing a predictive model to identify recipes likely to generate high site traffic. Tasty Bytes, a subscription-based recipe discovery platform, has observed up to a 40% increase in website traffic when a popular recipe is featured on the homepage. The challenge was to replace the subjective selection of homepage recipes with a data-driven approach, aiming for a prediction accuracy of at least 80% for identifying high-traffic recipes.

This project utilized recipe data, including attributes such as calories, macronutrients, servings, and historical traffic outcomes. A key step was analyzing the relationships between these features to uncover insights and build a predictive model for optimizing recipe selection.

---

## Executive Summary
This report outlines the findings from analyzing Tasty Bytes recipe data and building a predictive model for homepage recipe selection. Key insights include:
- **Correlations with High Traffic:** High-traffic recipes showed a positive correlation with calories and protein content and a moderate negative correlation with serving size.
- **Model Performance:** A random forest model achieved 83% accuracy in predicting high-traffic recipes.
- **Operational Impact:** Recommendations focus on refining recipe selection and tracking performance metrics to enhance user engagement and subscription growth.

These findings enable actionable strategies to improve site performance and align recipe promotion with user preferences.

---

## Insights Deep-Dive

### Data Validation & Cleaning
- **Validation:** All columns were verified for consistency and completeness.
- **Cleaning Steps:**
  - Imputed missing values in numerical columns with medians.
  - Normalized recipe categories to ensure consistent grouping.
  - Identified and resolved outliers using interquartile ranges.

### Exploratory Analysis
- **Correlation Analysis:**
  - A heatmap of feature correlations revealed:
    - A strong positive correlation (+0.68) between **calories** and high traffic.
    - A moderate positive correlation (+0.53) between **protein content** and high traffic.
    - A slight negative correlation (-0.32) between **servings** and high traffic.
  - Carbohydrate content showed minimal correlation with high-traffic outcomes (+0.12).
- **Insights from Correlation Heatmap:**
  - Recipes higher in calories and protein are more likely to attract traffic.
  - Larger serving sizes are less likely to drive high traffic, suggesting that smaller, more personalized recipes perform better.

![Correlation Matrix for High-Traffic Recipes](insert_image_link_here)

### Model Development
- **Problem Definition:** A classification problem to predict whether a recipe will generate high traffic.
- **Baseline Model:** A decision tree classifier achieved 76% accuracy.
- **Comparison Model:** A random forest model achieved superior accuracy at 83%, with an F1 score of 81%.

### Model Evaluation
- **Performance Metrics:**
  - Random Forest:
    - Accuracy: 83%
    - Precision: 81%
    - Recall: 79%
    - F1 Score: 81%
- The random forest model demonstrated reliable predictions and is recommended for operational use.

---

## Metric Definition
To monitor recipe traffic performance, the **High Traffic Rate (HTR)** metric was defined:
\[
HTR = \frac{\text{High Traffic Recipes Featured}}{\text{Total Recipes Featured}}
\]
- **Baseline HTR:** Based on current data, HTR is approximately 52%.

---

## Recommendations
1. **Implement Predictive Model:** Deploy the random forest model to automate recipe selection for the homepage.
2. **Focus on Calorie- and Protein-Dense Recipes:** Promote recipes with higher calorie and protein content to maximize traffic potential.
3. **Monitor High Traffic Rate (HTR):** Establish monthly tracking of the HTR metric to evaluate model performance and adjust strategies.
4. **Iterate and Refine:** Update the model regularly with new data to ensure it reflects evolving user preferences and traffic patterns.

---

## Key Questions for Stakeholders
- Should we factor in recipe preparation time or cost into the prediction model?
- What is the desired balance between traffic generation and recipe diversity on the homepage?
- How frequently should we update the predictive model with new data?

---

## Assumptions and Caveats
- Correlations are based on historical data and may not account for future shifts in user preferences.
- The heatmap analysis is limited to numerical features, excluding potential qualitative influences like ingredient appeal.
- The model’s performance is contingent on the quality and representativeness of the current dataset.

For further details, refer to the accompanying notebook, which includes code, visualizations, and step-by-step analysis.
