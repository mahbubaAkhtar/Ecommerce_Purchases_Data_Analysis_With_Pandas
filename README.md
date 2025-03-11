# 🛒 Ecommerce_Purchases_Data_Analysis_With_Pandas

## 📊 Customer Purchase Data Analysis
## 🔍 Overview
This project focuses on analyzing customer purchase data to uncover patterns in customer behavior, spending habits, and demographic insights. The study includes data preprocessing, exploratory analysis.
## ⚙️ Requirements
🔹 Python 3.x

🔹 Jupyter Notebook

🔹 Libraries: Pandas

## 🚀 How to Use

🔹 Install dependency: `pip install pandas`

🔹 Open `Cust_Purch_Data_Exercise.ipynb` in Jupyter Notebook

🔹 Run each cell sequentially to execute the analysis

## 📂 Dataset Description
The dataset used for this project is `Cust_Purch_FakeData.csv`. It contains customer information, including names, phone numbers, professions, spending amounts, and credit card details.
- `Entries`: 30,000 records
- `Columns`: 20 attributes including customer details, purchase history, and demographic information.
## 📂 Project Structure
```
├── Cust_Purch_Data_Exercise.ipynb  # Jupyter Notebook with all solutions
├── data                            # Directory for dataset (if needed)
│   ├── Cust_Purch_FakeData.csv
├── README.md                       # Documentation
```
## 🔑 Key Fields:
- 👤 `first, last, email, phone` - Customer identity details
- 🎂 `age, gender, profession` - Demographic attributes
- 🏢 `company, province, postal` - Location & workplace
- 💰 `price(CAD)` - Purchase amount
- ⏳ `date, weekday, ampm` - Transaction time
- 🎨 `fav_color, ip` - Additional attributes
## 📈 Analysis Performed
 - 🛠 Data Cleaning: Handling missing values, fixing data types.
 - 📊 Exploratory Data Analysis (EDA):
   - Customer demographic insights
   - Spending trends based on age, gender, and location
   - High-value customer identification
### Question - 1. Import Pandas and Read the csv file.
   #####  `Code` : 
 ![1](https://github.com/user-attachments/assets/531c1101-408b-478a-9a1f-64b97bc79b39)

   ##### `Explanation`: Importing the Pandas library and loading the dataset into a DataFrame object is the first crucial step in our analysis journey.



