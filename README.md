# Hotel Booking Analysis and Cancellation Prediction 🏨

This project analyzes a hotel booking dataset to uncover key insights
and build a machine learning model to predict booking cancellations. The
goal is to help hotels understand booking patterns, reduce revenue loss
from cancellations, and improve their operational efficiency.

This project was developed as part of my professional growth, leveraging
skills I acquired during my internship at **Genius Technology Center
(GTC)**. I am grateful for the invaluable experience and mentorship I
received there.

## 📝 Project Overview

The project is divided into three main phases:

1.  **Exploratory Data Analysis (EDA)**: I started by cleaning and
    exploring the dataset to understand its structure, identify missing
    values, and uncover initial patterns. I used visualizations to
    highlight trends related to hotel types, booking times, and customer
    behaviors.
2.  **Data Preprocessing and Feature Engineering**: After cleaning the
    data, I engineered new features to enhance the predictive power of
    the machine learning model. This involved creating features like
    `total_stay`, `total_guests`, and applying transformations such as
    log scaling and one-hot encoding.
3.  **Machine Learning Modeling**: I built and evaluated several
    classification models to predict whether a booking would be
    canceled. The final model, a Gradient Boosting Classifier,
    demonstrated strong performance in identifying potential
    cancellations.

------------------------------------------------------------------------

## ⚡ Challenges and Solutions

During this project, I encountered several challenges. Here's how I
tackled them:

### **1. Handling Missing Data** 🧩

-   **Difficulty**: The dataset contained missing values in columns like
    `country`, `agent`, and `company`. The `company` column, in
    particular, had over 90% of its values missing.\
-   **Solution**: For `country` and `agent`, which had a smaller number
    of missing values, I filled the gaps with the mode (the most
    frequent value). For the `company` column, due to the sheer volume
    of missing data, I decided to drop it entirely as it would not have
    contributed meaningfully to the model.

### **2. Dealing with Outliers** 📊

-   **Difficulty**: The `adr` (Average Daily Rate) column had some
    extreme outliers, including a value of 5400, which was highly
    unrealistic for a typical hotel booking. These outliers could skew
    the analysis and negatively impact the model's performance.\
-   **Solution**: I identified and removed these outliers by setting a
    reasonable threshold based on the data distribution. I filtered out
    bookings where the ADR was above a certain percentile, ensuring that
    the data used for analysis and modeling was more representative of
    typical booking prices.

### **3. Feature Engineering Complexity** 🛠️

-   **Difficulty**: The raw data wasn't immediately ready for machine
    learning. I needed to transform categorical data and create new,
    more informative features from the existing ones.\
-   **Solution**:
    -   I combined `stays_in_weekend_nights` and `stays_in_week_nights`
        to create a `total_nights` feature.\
    -   I created a `total_guests` feature by summing `adults`,
        `children`, and `babies`.\
    -   For categorical features like `meal`, `market_segment`, and
        `deposit_type`, I applied one-hot encoding to convert them into
        a numerical format that the machine learning models could
        understand.

------------------------------------------------------------------------

## 💡 Key Insights from the Analysis

### **Which month has the highest number of cancellations?**

-   **Insight**: The highest number of cancellations occurs in
    **August**, which is also the busiest month for bookings.\
-   **Recommendation**: Hotels could implement more flexible
    cancellation policies during off-peak months while considering
    stricter policies or higher non-refundable deposits for peak months
    like August.

### **Does the lead time affect cancellations?**

-   **Insight**: Yes, there is a strong correlation between **lead
    time** and cancellations. Bookings made far in advance are much more
    likely to be canceled.\
-   **Recommendation**: Hotels should pay closer attention to bookings
    with long lead times. They could engage these customers with
    reminder emails or special offers closer to their check-in date.

### **What is the cancellation rate for repeated guests vs. new guests?**

-   **Insight**: **New guests** have a significantly higher cancellation
    rate compared to **repeated guests**. Loyal customers are far less
    likely to cancel their bookings.\
-   **Recommendation**: Focusing on customer loyalty programs and
    providing excellent service to first-time guests could turn them
    into repeat customers, thereby reducing the overall cancellation
    rate.

------------------------------------------------------------------------

## 🤖 Machine Learning Model

To predict booking cancellations, I trained several models, including
Logistic Regression, Decision Tree, and Gradient Boosting. The
**Gradient Boosting Classifier** emerged as the top-performing model
with the following metrics:

-   **Accuracy**: \~93%\
-   **Precision**: High precision in identifying true cancellations.\
-   **Recall**: Strong ability to catch most of the actual
    cancellations.

This model can be integrated into the hotel's booking system to flag
high-risk bookings in real-time, allowing staff to take proactive
measures.

------------------------------------------------------------------------

## 🙏 Acknowledgments

I want to extend my sincere gratitude to the **Genius Technology Center ([GTC](https://www.linkedin.com/company/genius-technology-center/))**
 for the internship opportunity. The skills and knowledge I
gained in data analysis, feature engineering, and machine learning
during my time there were instrumental in the successful completion of
this project.

------------------------------------------------------------------------

## 🚀 Future Work

-   Add hyperparameter tuning with GridSearchCV for model optimization\
-   Deploy the model with a Flask or FastAPI web app\
-   Test the model with real-time booking data to evaluate performance
    in production
