## Customer Lifetime Value (CLV) Prediction with Cohort Analysis

### Project Overview
In the competitive e-commerce landscape, understanding customer value is crucial for sustainable growth. This project provides an end-to-end framework for predicting Customer Lifetime Value (CLV), a metric that estimates the total revenue a business can reasonably expect from a single customer account. By forecasting future customer value, businesses can move beyond simple historical analysis and make proactive, data-driven decisions.

The core objective is to identify and segment high-value customers to inform targeted marketing campaigns, personalize customer experiences, and improve retention strategies. The project begins with an in-depth cohort analysis to understand customer loyalty, followed by RFM (Recency, Frequency, Monetary) feature engineering. Finally, it leverages probabilistic models—specifically the BG/NBD and Gamma-Gamma models—to predict future purchasing behavior and monetary value, culminating in a actionable CLV forecast for each customer.

### Technical Skills
  1. **Languages & Libraries:** Python, Pandas, NumPy, Matplotlib, Seaborn, Lifetimes
  2. **Techniques:** Data Cleaning, Exploratory Data Analysis (EDA), Cohort Analysis, RFM Feature Engineering, Statistical Modeling, Customer Segmentation
  3. **Probabilistic Models:** Beta-Geometric/Negative Binomial Distribution (BG/NBD) for transaction prediction and the Gamma-Gamma model for monetary value prediction.
  4. **Visualization:** Tableau for interactive dashboards and Matplotlib/Seaborn for static plots within the analysis notebook.

### Project Structure
Customer_Lifetime_Value_Prediction/
|
|-- clv_env/                  # Virtual environment (ignored by Git)
|-- online_retail_II.xlsx     # Raw data file (ignored by Git)
|-- clv_dashboard_data.csv    # Cleaned data for Tableau (ignored by Git)
|-- analyze_data.ipynb        # Jupyter Notebook with the full analysis
|-- .gitignore                # Specifies files to be ignored by Git
|-- README.md                 # This file
|-- requirements.txt          # dependencies required for successful execution of the project

### Methodology
The project follows a structured methodology, moving from raw data to actionable customer segments.

1. **Data Cleaning and Preparation**
The initial dataset, containing transactional data, required significant preprocessing. The raw data was cleaned by filtering out records with missing Customer IDs, removing negative-quantity entries corresponding to canceled orders, and excluding zero-value transactions. This ensured a clean, reliable dataset for modeling.

2. **Cohort Analysis for Retention Insights**
To understand customer behavior over time, customers were grouped into cohorts based on their first purchase month. A retention matrix and a corresponding heatmap were generated to visualize how well each cohort was retained in subsequent months. This analysis provided crucial insights into seasonal trends and the long-term evolution of customer loyalty.

3. **RFM Feature Engineering**
Transactional data was aggregated to a customer-level view using Recency, Frequency, and Monetary (RFM) metrics. The lifetimes library was used to efficiently calculate:

  1. **Recency:** The age of the customer at their last purchase.
  2. **Frequency:** The number of repeat purchases.
  3. **T:** The age of the customer at the end of the observation period.
  4. **Monetary Value:** The average value of a customer's purchases.

4. **Probabilistic Modeling**
Two powerful probabilistic models were employed to predict customer behavior:

  1. **BG/NBD Model:** This model was trained on customer recency, frequency, and age (T) data to predict the expected number of future transactions for each customer. It effectively models the process of customers "dying" or becoming inactive.
  2. **Gamma-Gamma Model:** This model was trained on customer frequency and monetary data to estimate the average monetary value of a customer's future transactions. It works by assuming that monetary value follows a Gamma distribution.

5. **CLV Calculation and Customer Segmentation**
The outputs of the BG/NBD and Gamma-Gamma models were combined to forecast the 12-month Customer Lifetime Value (CLV) for each customer. Based on these CLV scores, customers were segmented into four actionable tiers: "VIP," "High-Value," "Medium-Value," and "Low-Value." This segmentation allows the business to tailor marketing efforts, such as offering exclusive perks to VIPs or launching re-engagement campaigns for low-value customers.

### How to Run
Clone the repository:

git clone https://github.com/prakhar845/Customer-Lifetime-Value-Prediction.git
cd Customer-Lifetime-Value-Prediction

**Set up the environment:**

python -m venv clv_env
source clv_env/bin/activate  # On Windows: clv_env\Scripts\activate
pip install -r requirements.txt

**Download the data:** Download the "Online Retail II" dataset from the UCI Machine Learning Repository and place the .xlsx file in the project's root directory.

**Run the analysis:** Open and run the analyze_data.ipynb Jupyter Notebook to perform the full analysis, train the models, and generate CLV predictions.

## Contributing
Contributions are welcome! If you have suggestions for improvements, new analysis ideas, or bug fixes, please:

1. Fork the repository.
2. Create a new branch (git checkout -b feature/your-feature-name).
3. Make your changes and commit them (git commit -m 'Add new feature').
4. Push to the branch (git push origin feature/your-feature-name).
5. Open a Pull Request.


Download the data: Download the "Online Retail II" dataset from the UCI Machine Learning Repository and place the .xlsx file in the project's root directory.

Run the analysis: Open and run the analyze_data.ipynb Jupyter Notebook.
