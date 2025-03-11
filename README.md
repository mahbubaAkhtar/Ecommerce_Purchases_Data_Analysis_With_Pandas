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

### **Question 1: Import Pandas and Read the CSV File**
**Code:**
```python
import pandas as pd
df = pd.read_csv('Cust_Purch_FakeData.csv')
```
**Explanation:**  Importing the Pandas library and loading the dataset into a DataFrame object is the first crucial step in our analysis journey.

---

### **Question 2: Its good idea to see how the data look like, display first 5 rows of your data-set.**
**Code:**
```python
df.head(5)
```
**Explanation:** Visualizing the first few rows helps us understand the structure and format of our dataset before diving into deeper analysis. 

---

### **Question 3: How many entries your data have? Can you tell the no. of columns in your data?**
**Code:**
```python
df.info()
```
**Explanation:** The dataset contains 30,000 entries with 20 columns, each representing different attributes related to customer purchases. The df.info() function provides an overview of the dataset by displaying the number of rows and columns, column names, data types, and the count of non-null values for each column. It also indicates the memory usage of the dataset, helping to understand its structure and potential missing values. This function is particularly useful for quickly assessing the quality and completeness of the data before performing further analysis.

---

### **Question 4: What are the max and min ages of your customer? Can you find mean of your customer?**
**Code:**
```python
print("Max. age of the customer is:  ", df['age'].max() )
print("Min. age of the customer is:  ", df['age'].min() )
print("Avg. age of the customer is:  ", df['age'].mean() )
```
**Explanation:** The code calculates the maximum, minimum, and average ages of customers using `df['age'].max(), df['age'].min(), and df['age'].mean()`. These operations analyze the 'age' column in the dataset, providing a summary of the age distribution among customers.

---

### **Question 5:  What are the three most common customer's names?**
**Code:**
```python
df['first'].value_counts().head(3)
```
**Explanation:** The code identifies the three most common first names in the dataset. It uses `df['first'].value_counts().head(3)` to count the frequency of each name and extract the top three most frequent ones, providing a quick summary of the most common customer names. 

---

### **Question 6:  Two customers have the same phone number, can you find those customers?**
**Code:**
```python
df[df['phone'] == '(263) 382-8004']
```
- **Explanation:** The code counts how often each unique phone number appears in the 'phone' column.It uses `df['phone'].value_counts()` to show the frequency of each number, helping identify duplicates or patterns in customer phone data.

---

### **Question 7:  How many customers have profession "Structural Engineer"?**
**Code:**
```python
df[df['profession'] == 'Structural Engineer'].count()
```
**Explanation:** The code counts customers with the profession "Structural Engineer" using `df[df['profession'] == 'Structural Engineer'].count()`. It filters rows where the 'profession' column matches "Structural Engineer" and counts the results, providing the total number of customers with that profession.  

---

### **Question 8: How many male customers are 'Structural Engineer'?**
**Code:**
```python
df1 = df[df['profession'] == 'Structural Engineer']
df1[df1['gender'] == 'Male'].count()
```
**Explanation:**  The code counts male customers with the profession "Structural Engineer". It first filters rows where 'profession' is "Structural Engineer" into `df1`, then filters `df1` for 'gender' == "Male" and counts the results, giving the total number of male Structural Engineers.

### **Question 9: Find out the female Structural Engineers from province Alberta (AB)?**
**Code:**
```python
df2 = df1[df1['gender'] == 'Female']
df2[df2['province'] == 'AB']
```
**Explanation:** The code finds female Structural Engineers from Alberta (AB). It filters the dataset for "Structural Engineer" in the 'profession' column, then for "Female" in the 'gender' column, and finally for "AB" in the 'province' column, extracting the relevant customer data.

---

### **Question 10: What is the max, min and average spending?**
**Code:**
```python
print("Max. spending:  ", df['price(CAD)'].max() )
print("Mai. spending:  ", df['price(CAD)'].min() )
print("Avg. spending:  ", df['price(CAD)'].mean() )
```
 **Explanation:** The code calculates the max, min, and average spending from the 'price(CAD)' column using `df['price(CAD)'].max()`, `df['price(CAD)'].min()`, and `df['price(CAD)'].mean()`. It provides key statistics about customer spending in the dataset.

---

### **Question 11: Who did not spend anything? Company wants to send a deal to encourage the customer to buy stuff!**
**Code:**
```python
df[df['price(CAD)'] == 0]
```
**Explanation:** The code identifies customers who did not spend anything (spending = 0) by filtering the dataset where the 'price(CAD)' column equals 0. This helps the company target these customers with special deals to encourage purchases.

---

### **Question 12:  As a loyalty reward, company wants to send thanks coupon to those who spent 100CAD or more, please find out the customers?**
**Code:**
```python
df[df['price(CAD)'] >= 100]
```
**Explanation:** The code identifies customers who spent 100 CAD or more by filtering the dataset where the 'price(CAD)' column is greater than or equal to 100. This helps the company target loyal customers for sending thanks coupons as a reward.

---

### **Question 13:  How many emails are associated with this credit card number '5020000000000230'?**
**Code:**
```python
df[df['cc_no'] == 5020000000000230]['email']
```
**Explanation:** The code finds the emails associated with the credit card number '5020000000000230' by filtering the dataset where the 'cc_no' column matches the specified number and then extracting the 'email' column. This helps identify the email addresses linked to that credit card.

---

### **Question 14:  We need to send new cards to the customers well before the expire, how many cards are expiring in 2019?**
**Code:**
```python
df[df['cc_exp'].str.endswith('19')].count()
```
**Explanation:** The code counts the number of credit cards expiring in 2019 by filtering the 'cc_exp' column where the expiration year ends with '19' and then counting the corresponding rows. This helps identify how many customers need new cards before expiration.

---

### **Question 15: How many people use Visa as their Credit Card Provider?**
**Code:**
```python
df[df['cc_type'] == 'Visa']['first'].count()
```
**Explanation:** The code counts the number of customers who use Visa as their credit card provider by filtering the 'cc_type' column for "Visa" and then counting the corresponding rows. This provides the total number of Visa users in the dataset.

---

### **Question 16: Can you find the customer who spent 100 CAD using Visa?**
**Code:**
```python
df5 = df[df['cc_type'] == 'Visa']
df5[df5['price(CAD)'] == 100]
```
**Explanation:** The code identifies customers who spent exactly 100 CAD using a Visa credit card. It first filters the dataset for rows where the 'cc_type' column is "Visa" and stores the result in `df5`. Then, it filters `df5` for rows where the 'price(CAD)' column equals 100, pinpointing the specific customers who meet both criteria.

---

### **Question 17: What are two most common professions?**
**Code:**
```python
df['profession'].value_counts().head(2)
```
**Explanation:** The code identifies the two most common professions in the dataset by counting the frequency of each unique value in the 'profession' column using `value_counts()` and then selecting the top two results with `.head(2)`. This provides a quick summary of the most frequent professions among customers.

---

### **Question 18: Can you tell the top 5 most popular email providers? (e.g. gmail.com, yahoo.com, etc...)**
**Code:**
```python
df['email'].str.split('@').str[1].value_counts().head(5)
```
**Explanation:** The code finds the top 5 most popular email providers by splitting the 'email' column at '@', extracting the domain, counting their frequency with `.value_counts()`, and selecting the top 5 with `.head(5)`. This summarizes the most common email services used by customers.

---

### **Question 19: Is there any customer who is using email with "am.edu"?**
**Code:**
```python
df[df['email'].str.endswith('am.edu')]
```
**Explanation:** The code checks if any customer is using an email ending with "am.edu" by filtering the 'email' column with `.str.endswith('am.edu', na=False)`. This identifies rows where the email domain matches "am.edu", if any exist.

---

### **Question 20: Which day of the week, the store gets more customers?**
**Code:**
```python
df['weekday'].value_counts().head()
```
**Explanation:** The code determines the day of the week with the most customers by counting the frequency of each unique value in the 'weekday' column using `.value_counts()` and then displaying the top results with `.head()`. This identifies the busiest day(s) for the store.

---



## ✍Author
### Mahbuba AKhtar Jidni
