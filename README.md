# Sentiment Analysis of Movie Reviews  

## Project Overview  
This project aims to classify the sentiment of movie reviews using an imbalanced textual dataset. Extensive preprocessing, exploratory data analysis (EDA), feature engineering, and modeling techniques were applied to achieve optimal results. The project was part of a competition, where the final solution achieved **84% accuracy**, ranking in the top 20 out of 700 participants.  

---

## Dataset Description  
The dataset contains **162,758** records with the following features:  

1. **movieid**: Unique identifier for the movie (object)  
2. **reviewerName**: Name of the reviewer (object)  
3. **isFrequentReviewer**: Indicates if the reviewer frequently reviews movies (bool)  
4. **reviewText**: Text of the review (object)  
5. **sentiment**: Target label indicating sentiment (e.g., positive, negative, neutral) (object)  
6. **audienceScore**: Audience score for the movie (float64)  
7. **runtimeMinutes**: Duration of the movie in minutes (float64)  
8. **genre**: Genre of the movie (object)  
9. **originalLanguage**: Language of the movie (object)  
10. **director**: Director of the movie (object)  

---

## Data Preprocessing  

1. **Handling Missing Values**:  
   - Missing values were imputed using techniques such as:  
     - **Mean** for numerical columns  
     - **Mode** for categorical columns  
     - **Empty strings** for text columns  

2. **Text Cleaning**:  
   - Applied regular expressions (Regex) to clean and normalize textual data:  
     - Removed numerical values from the text (`r'\d+'`).  
     - Eliminated repeated consecutive characters (e.g., "soooo" -> "so") using a regex pattern for character repetition (`(.)\1{2,}`).  

   > **Concepts of Regex:**  
   - **`\d+`**: Matches one or more digits.  
   - **`(.)\1{2,}`**: Captures a character and identifies its repetition two or more times, replacing it with a single instance.  

---

## Feature Engineering  

1. **CountVectorizer**:  
   - Converted textual data into a bag-of-words representation for model input.  

2. **One-Hot Encoding (OHE)**:  
   - Encoded categorical variables into binary format.  

3. **MaxAbsScaler**:  
   - Scaled numerical data to a range of -1 to 1 while preserving sparsity.  

4. **MultiLabelBinarizer**:  
   - Transformed multilabel data into binary format for classification tasks.  

---

## Modeling  

### Algorithms Used:  
1. **Logistic Regression**  
2. **XGBoost**  
3. **Random Forest**  
4. **Multinomial Naive Bayes**  

### Hyperparameter Tuning:  
- Used **GridSearchCV** to optimize hyperparameters for all models.  

### Evaluation Metrics:  
- **Confusion Matrix**: Analyzed true positives, false positives, true negatives, and false negatives.  
- **ROC-AUC Curve**: Evaluated the area under the curve for model performance across different thresholds.  

---

## Conclusion  

This project demonstrates the effective use of text preprocessing, feature engineering, and machine learning models to address an imbalanced sentiment analysis problem. The integration of advanced techniques like hyperparameter tuning and robust evaluation metrics contributed significantly to achieving competitive results.
