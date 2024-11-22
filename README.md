# Recipe Traffic Prediction for Tasty Bytes

## Project Background
As a data scientist for Tasty Bytes, I was tasked with developing a predictive model to identify recipes likely to generate high site traffic. Tasty Bytes, a subscription-based recipe discovery platform, has observed up to a 40% increase in website traffic when a popular recipe is featured on the homepage. The challenge was to replace the subjective selection of homepage recipes with a data-driven approach, aiming for a prediction accuracy of at least 80% for identifying high-traffic recipes.

The project leveraged data on recipe attributes such as calories, macronutrients, category, and servings, along with historical traffic performance. By analyzing this data, the goal was to uncover insights and build a reliable model to optimize recipe selection, driving traffic and subscription growth.

---

## Executive Summary
This report outlines the process and findings from analyzing Tasty Bytes recipe data and building a predictive model for homepage recipe selection. Key insights include:
- **High Traffic Prediction:** A classification model was developed and achieved an accuracy of 83% in predicting high-traffic recipes.
- **Key Influencers:** Recipe category, calorie content, and serving size were significant predictors of traffic outcomes.
- **Operational Impact:** A metric for monitoring recipe traffic was defined, establishing a baseline for future tracking.

These findings form the basis for actionable recommendations to improve site performance and customer engagement.

---

## Insights Deep-Dive

### Data Validation & Cleaning
- **Validation:** Verified integrity and consistency of all columns against provided data schema.
- **Cleaning Steps:**
  - Handled missing values in numerical fields by imputing medians.
  - Normalized category names to ensure uniformity.
  - Identified and resolved outliers in calorie and macronutrient values using interquartile ranges.

### Exploratory Analysis
- **Single-variable Insights:**
  - Recipes in the 'Dessert' and 'Breakfast' categories were most frequently associated with high traffic.
  - High-calorie recipes tended to attract more traffic, with a median of 350 calories per serving.
- **Multi-variable Insights:**
  - High-traffic recipes were most common in 'Dessert' and 'Lunch/Snacks' categories, with an optimal serving size of 4-6.

### Model Development
- **Problem Definition:** This is a classification problem, aiming to predict if a recipe will generate high traffic ('High') or not.
- **Baseline Model:** A decision tree classifier achieved 76% accuracy.
- **Comparison Model:** A random forest classifier outperformed the baseline with an accuracy of 83% and a precision of 81%.

### Model Evaluation
- **Metrics:** Accuracy, precision, recall, and F1 score were used for evaluation.
- **Performance Comparison:**
  - Baseline (Decision Tree): Accuracy = 76%, F1 Score = 73%.
  - Random Forest: Accuracy = 83%, F1 Score = 81%.

### Metric Definition
To monitor traffic performance, the **High Traffic Rate (HTR)** metric was defined as:
\[
HTR = \frac{\text{High Traffic Recipes Featured}}{\text{Total Recipes Featured}}
\]
- **Initial Value:** Based on current data, HTR is estimated at 52%.

---

## Recommendations
1. **Implement Predictive Model:** Integrate the random forest model into recipe selection workflows to automate homepage recipe decisions.
2. **Monitor High Traffic Rate (HTR):** Establish a baseline HTR and track performance monthly to assess model effectiveness.
3. **Optimize Content Strategy:** Focus on promoting 'Dessert' and 'Breakfast' recipes with higher calorie counts and serving sizes of 4-6 to maximize traffic.
4. **Iterate Model Development:** Regularly update the model with new traffic data to improve prediction accuracy and adapt to changing trends.

---

## Key Questions for Stakeholders
- How often will the predictive model be updated with new recipe and traffic data?
- Should seasonal factors (e.g., holidays) influence the recipe selection process?
- What is the acceptable trade-off between high-traffic prediction accuracy and user engagement metrics (e.g., recipe diversity)?

---

## Assumptions and Caveats
- Traffic data assumes uniform quality and does not account for external influences such as marketing campaigns.
- The model's performance is based on historical data and may require retraining for future applicability.
- The HTR metric reflects high-traffic performance but does not directly account for subscription conversions.

---

For further details, refer to the accompanying notebook with data cleaning, analysis, model development, and evaluation steps.
