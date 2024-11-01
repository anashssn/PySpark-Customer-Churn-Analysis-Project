# PySpark Customer Churn Analysis Project

This project aims to analyze customer churn for a telecommunications company using PySpark. By examining factors such as customer demographics, usage behavior, and service interactions, we create a predictive model to identify customers likely to churn. This analysis is intended to help the business develop effective retention strategies for valuable customers.

## Project Overview

Customer churn is a significant challenge in the telecommunications industry. This project identifies key factors driving customer churn and provides insights through:
- Data Preprocessing
- Exploratory Data Analysis (EDA)
- Feature Engineering
- Predictive Modeling and Evaluation

## Project Structure

- **Data Preprocessing**: Cleaned and preprocessed the data by handling missing values, encoding categorical variables, and scaling features.
- **Exploratory Data Analysis**: Visualized trends and correlations among key variables to gain insights into churn patterns.
- **Feature Engineering**: Engineered features from the raw data to improve model performance.
- **Predictive Modeling**: Trained a Decision Tree model to classify and predict customer churn.
- **Model Evaluation**: Evaluated model performance using metrics to assess its accuracy in predicting churn.

## Technologies Used

- **PySpark**: Primary framework for large-scale data processing and analysis.
- **Pandas**: Data manipulation and transformation.
- **Matplotlib & Plotly**: Data visualization for trend analysis and insights.

## Getting Started

1. **Environment Setup**: Ensure that PySpark, Pandas, Matplotlib, and Plotly are installed.  
   ```bash
   pip install pyspark pandas matplotlib plotly
   ```

2. **Data Loading**: Use PySpark’s SparkSession to load and process data efficiently for large datasets.

3. **Key Steps**:
   - **Data Preprocessing**: Handled missing values using `Imputer`, encoded categorical data with `StringIndexer`, and assembled features with `VectorAssembler`.
   - **Exploratory Data Analysis (EDA)**: Used Plotly and Matplotlib for visualizing trends in customer behavior.
   - **Feature Engineering**: Scaled features with `StandardScaler`.
   - **Modeling**: Trained a Decision Tree Classifier and evaluated it using `BinaryClassificationEvaluator`.

### Example Code Snippets

```python
# Importing Spark session
from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("CustomerChurnAnalysis").getOrCreate()

# Loading data
data = spark.read.csv("path/to/your/data.csv", header=True, inferSchema=True)

# Data Preprocessing
from pyspark.ml.feature import Imputer
imputer = Imputer(inputCols=["age", "income"], outputCols=["age_imputed", "income_imputed"])
data = imputer.fit(data).transform(data)
```

## Results and Insights

- **Churn Factors**: Identified key factors contributing to customer churn, such as service usage frequency and customer service interactions.
- **Model Performance**: The Decision Tree model achieved a good balance of accuracy and interpretability, making it suitable for practical applications in churn prediction.

## Future Enhancements

- Experiment with other models like Random Forests or Gradient Boosting for improved accuracy.
- Integrate additional data sources for deeper insights (e.g., social media data).
- Deploy the model in a real-time prediction pipeline to identify at-risk customers dynamically.

## Dependencies

- `pyspark`
- `pandas`
- `matplotlib`
- `plotly`

## Contact

For any inquiries or suggestions, please reach out via email: anashssn@gmail.com
