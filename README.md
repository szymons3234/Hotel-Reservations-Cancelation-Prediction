# Hotel Reservations Cancellation Prediction

This project aims to predict hotel reservation cancellations to assist hotels in improving their booking and revenue management. By analyzing the factors that contribute to cancellations, hotels can reduce revenue losses and optimize operations.

## Table of Contents
1. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
2. [Data Processing](#data-processing)
3. [Model Building](#model-building)
4. [Model Evaluation](#model-evaluation)
5. [Conclusion](#conclusion)

## Exploratory Data Analysis (EDA)

EDA was performed to understand the dataset and uncover patterns that could influence the prediction model. Key findings from the analysis are:

### Guest Information:
- Majority of bookings were made for **2 adults with no children** (likely couples), followed by **1 adult with no children** (likely business trips).

### Time Spent at Hotel:
- Most bookings were made for **weeknights**, with fewer bookings for weekends.
- **Weekend bookings** had **lower cancellation rates** compared to weeknight bookings.

### Cancellation Analysis:
- **Bookings with fewer nights**, especially on weekdays, had higher cancellation rates.
- **Reservations with longer lead times** were more likely to be canceled.

### Market Segment:
- **Online platforms** had the most reservations and cancellations, suggesting that online reputation plays a significant role in cancellations.

## Data Processing

1. **Outlier Removal**:
   - Outliers in the `lead_time` and `avg_price_per_room` columns were removed using the **Interquartile Range (IQR)** method.

2. **Label Encoding**:
   - Categorical columns such as `meal_type`, `room_type`, `market_segment`, and `booking_status` were encoded using **LabelEncoder**.

3. **Feature Scaling**:
   - Columns `lead_time` and `avg_price_per_room` were standardized using **StandardScaler**.

4. **Train-Test Split**:
   - The dataset was split into training and testing sets (80% for training, 20% for testing).

## Model Building

Several classification models were built to predict reservation cancellations:

1. **Decision Tree Classifier**:
   - A decision tree model was built and hyperparameters were tuned using **GridSearchCV** for optimal performance.

2. **Random Forest Classifier**:
   - A random forest model was built, with hyperparameters tuned using **GridSearchCV**.

3. **Logistic Regression**:
   - A logistic regression model was built and tuned for hyperparameters using **GridSearchCV**.

## Model Evaluation

The models were evaluated using the following metrics:

1. **Confusion Matrix Heatmap**:
   - For each model, a **confusion matrix heatmap** was plotted to visualize true positives, false positives, true negatives, and false negatives.

2. **Classification Report**:
   - The **precision**, **recall**, **F1-score**, and **accuracy** were computed for each model.

3. **Model Metrics**:
   - **Accuracy Score**, **Mean Absolute Error**, and **Mean Squared Error** were calculated for each model.

### Model Performance:

- **Decision Tree Classifier**:
  - **Accuracy**: 84.6%
  - **F1-Score**: 0.89 for canceled reservations
  - **Precision**: 0.87, **Recall**: 0.91

- **Random Forest Classifier**:
  - **Accuracy**: 83.4%
  - **F1-Score**: 0.89 for canceled reservations
  - **Precision**: 0.83, **Recall**: 0.95

- **Logistic Regression**:
  - **Accuracy**: 78.8%
  - **F1-Score**: 0.85 for canceled reservations
  - **Precision**: 0.81, **Recall**: 0.89

## Conclusion

Key insights from the analysis:

1. **Guest Information and Cancellations**:
   - Bookings with children tend to have **lower cancellation rates**, while **couples** and **business trips** (1 adult) had **higher cancellations**.

2. **Impact of Lead Time**:
   - **Longer lead times** result in higher cancellation rates. Hotels should aim to **reduce lead times** to minimize cancellations.

3. **Market Segment**:
   - **Online bookings** had the highest cancellation rates. Improving **online reputation** could help reduce cancellations.

4. **Model Comparison**:
   - Among the models, the **Decision Tree Classifier** performed the best, achieving an accuracy of **84.6%**.

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Dataset: [Hotel Booking Demand Dataset](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand)
