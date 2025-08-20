Customer Lifetime Value (CLV) Prediction with Cohort Analysis

📈 Project Overview
This project focuses on predicting the Customer Lifetime Value (CLV) for an e-commerce business using a transactional dataset. The primary goal is to identify high-value customers and provide actionable business insights for targeted marketing and customer retention strategies. The project involves data cleaning, exploratory data analysis through cohort analysis, feature engineering (RFM), and the application of probabilistic models (BG/NBD and Gamma-Gamma) to forecast future customer value.

🛠️ Technical Skills
Languages & Libraries: Python, Pandas, NumPy, Matplotlib, Seaborn, Lifetimes

Techniques: Data Cleaning, Cohort Analysis, RFM Feature Engineering, Statistical Modeling

Models: Beta-Geometric/Negative Binomial Distribution (BG/NBD), Gamma-Gamma Model

Visualization: Tableau (or Matplotlib/Seaborn for static plots)

📂 Project Structure
Customer_Lifetime_Value_Prediction/
|
|-- clv_env/                  # Virtual environment (ignored by Git)
|-- online_retail_II.xlsx     # Raw data file (ignored by Git)
|-- clv_dashboard_data.csv    # Cleaned data for Tableau (ignored by Git)
|-- analyze_data.ipynb        # Jupyter Notebook with the full analysis
|-- .gitignore                # Specifies files to be ignored by Git
|-- README.md                 # This file

📋 Methodology
Data Cleaning: The raw transactional data was cleaned by handling missing Customer IDs, removing canceled orders, and filtering out zero-value transactions.

Cohort Analysis: Customers were grouped into cohorts based on their first purchase month. A retention heatmap was created to visualize how customer loyalty evolves over time.

RFM Feature Engineering: The transactional data was transformed into a customer-level summary table with Recency, Frequency, and Monetary (RFM) features using the lifetimes library.

Modeling:

The BG/NBD model was trained on recency and frequency data to predict future transaction frequency.

The Gamma-Gamma model was trained on frequency and monetary data to predict the average monetary value of future transactions.

CLV Calculation: The two models were combined to calculate the predicted 12-month CLV for each customer.

Customer Segmentation: Customers were segmented into "VIP," "High-Value," "Medium-Value," and "Low-Value" tiers based on their predicted CLV to enable targeted business actions.

🚀 How to Run
Clone the repository:

git clone https://github.com/prakhar845/Customer-Lifetime-Value-Prediction.git
cd Customer-Lifetime-Value-Prediction

Set up the environment:

python -m venv clv_env
source clv_env/bin/activate  # On Windows: clv_env\Scripts\activate
pip install -r requirements.txt

(Note: You will need to create a requirements.txt file by running pip freeze > requirements.txt in your activated environment.)

Download the data: Download the "Online Retail II" dataset from the UCI Machine Learning Repository and place the .xlsx file in the project's root directory.

Run the analysis: Open and run the analyze_data.ipynb Jupyter Notebook.