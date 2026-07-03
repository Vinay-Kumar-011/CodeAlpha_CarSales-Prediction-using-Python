# 📈 Sales Prediction using Python

Predicting product sales from advertising spend using regression models, with a focus on understanding which advertising channels actually drive revenue.

## 🎯 Objective

Businesses pour money into advertising across multiple channels — TV, radio, print — but not all channels are equally effective. This project builds a machine learning model to:

- Predict sales based on advertising spend across different platforms
- Identify which advertising channels have the greatest impact on sales
- Deliver actionable insights to guide marketing budget allocation

## 📊 Dataset

The dataset (`Advertising.csv`) contains 200 records of advertising spend (in thousands of dollars) across three channels, along with resulting sales figures (in thousands of units):

| Column | Description |
|---|---|
| TV | Advertising budget spent on TV |
| Radio | Advertising budget spent on radio |
| Newspaper | Advertising budget spent on newspaper |
| Sales | Product sales (target variable) |

**Source:** [Advertising Dataset on Kaggle](https://www.kaggle.com/datasets/vinayyadav011/advertising-csv)

## 🛠️ Approach

1. **Data Cleaning & Exploration**
   - Checked for missing values (none found) and inspected data types and distributions
   - Visualized relationships between each channel and sales using pairplots
   - Built a correlation heatmap to understand feature relationships

2. **Feature Selection**
   - Used `TV`, `Radio`, and `Newspaper` spend as predictors of `Sales`

3. **Modeling**
   - Split data into training (80%) and testing (20%) sets
   - Trained and compared two regression models:
     - Linear Regression
     - Random Forest Regressor

4. **Evaluation**
   - Compared models using R² Score and RMSE (Root Mean Squared Error)

| Model | R² Score | RMSE |
|---|---|---|
| Linear Regression | 0.899 | 1.782 |
| **Random Forest** | **0.981** | **0.769** |

The Random Forest model significantly outperformed Linear Regression, capturing non-linear relationships between advertising spend and sales.

5. **Feature Importance**
   - Analyzed which advertising channels most influence sales predictions using the Random Forest's feature importance scores

## 💡 Key Insights

- **TV advertising** is the strongest driver of sales, accounting for roughly **62%** of predictive importance
- **Radio advertising** is the second most influential channel, at roughly **36%**
- **Newspaper advertising** has minimal impact (~1%) on sales, suggesting diminishing returns on this channel
- The Random Forest model explains **98%** of the variance in sales (R² = 0.981), making it highly reliable for forecasting

## 📁 Recommendations for Marketing Strategy

- Prioritize and scale up **TV and radio** budgets, as they show the strongest correlation with sales lift
- Consider **reallocating newspaper spend** to higher-performing channels
- Use the trained model to simulate "what-if" scenarios (e.g., increasing TV budget by 20%) to forecast expected sales impact before committing budget

## 🧰 Tech Stack

- Python
- pandas, numpy — data manipulation
- matplotlib, seaborn — visualization
- scikit-learn — regression modeling & evaluation

## 📂 Project Structure

```
├── sales-prediction.ipynb   # Main notebook: EDA, modeling, evaluation, insights
├── Advertising.csv          # Dataset (download separately, see link above)
└── README.md                # Project documentation
```

## 🚀 How to Run

1. Download the dataset from the [Kaggle link](https://www.kaggle.com/datasets/vinayyadav011/advertising-csv) above
2. Place `Advertising.csv` in the project directory (update the file path in the notebook if needed)
3. Install dependencies:
   ```
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```
4. Run `sales-prediction.ipynb` cell by cell in Jupyter Notebook or JupyterLab

## 📌 Future Improvements

- Incorporate additional features such as target segment, platform/region, or seasonality if richer data becomes available
- Experiment with time-series forecasting models if sales-over-time data is added
- Tune Random Forest hyperparameters (e.g., via GridSearchCV) for further performance gains
- Deploy the model as a simple web app for interactive "what-if" budget planning
