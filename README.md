# Trader Behavior Insights – Market Sentiment Analysis

This project analyzes how Bitcoin market sentiment (Fear, Greed, Neutral,
Extreme Greed) influences trader performance on Hyperliquid. It explores
PnL behavior, trading volume, and skill-based performance under different
sentiment regimes.

---



---

## 📊 Datasets Used

### **1. Hyperliquid Historical Trades**

Includes fields such as:

* account
* execution\_price
* size\_tokens / size\_usd
* side
* closed\_pnl
* timestamp
* trade\_id

### **2. Fear–Greed Index**

Includes:

* timestamp (UNIX seconds)
* value (index 0–100)
* classification (Fear, Greed, Neutral, etc.)
* date

---

## 🧠 Methodology Overview

### **1. Data Cleaning**

* Standardized column names
* Parsed timestamps into datetime format
* Extracted date fields
* Dropped invalid rows

### **2. Merging**

Both datasets were merged **on daily dates**.

### **3. Feature Engineering**

Daily performance metrics per trader:

* trades\_count
* total\_pnl
* avg\_pnl
* win\_rate
* total\_volume\_usd
* avg\_size\_usd

### **4. Trader Skill Segmentation**

* Accounts active ≥ 3 days were grouped into:

  * Low skill
  * Medium skill
  * High skill

* Based on average daily PnL quantiles

### **5. Analysis Performed**

* Daily PnL vs Market Sentiment
* Average PnL vs Sentiment
* Trading Volume vs Sentiment
* PnL vs Sentiment \& Skill
* Logistic regression to predict profitable days

---

## 🔍 Key Insights From Graphs

### **1. Fear sentiment produces the highest trader profitability**

* Highest PnL spikes (~1.9M USD)
* Highest average PnL
* Highest trading volume

### **2. Greed is also profitable, but below Fear**

* Good PnL and high activity
* Not as volatile as Fear days

### **3. Neutral and Extreme Greed show low profitability**

* Markets stay quiet
* Fewer opportunities for large moves

### **4. High-skill traders dominate in all conditions**

* Very strong performance in Fear \& Greed
* Medium-skill traders rely heavily on volatile markets
* Low-skill traders lose or stay flat regardless of sentiment

### **5. Trading volume spikes dramatically in Fear**

* Traders deploy more capital during volatility
* Volume correlates with opportunity

---

## 📈 Visuals (saved in `visuals/` folder)

* pnl\_by\_sentiment.png
* avg\_pnl\_by\_sentiment.png
* trading\_volume\_by\_sentiment.png
* pnl\_by\_sentiment\_and\_skill.png

These plots are generated in the Jupyter notebook.

---

## 🧪 Predictive Model Summary

A logistic regression model was trained using:

* sentiment\_is\_greed
* trades\_count
* total\_volume\_usd
* win\_rate

Goal: predict if a trader-day is profitable.  
Model shows moderate predictive power — sentiment + behavior improves accuracy.

---

## ▶️ How to Run the Project

Install dependencies: pip install -r requirements.txt



Open the notebook: jupyter notebook notebooks/trader\_behavior\_analysis.ipynb





Run all cells in order.



---



\## 📮 Contact



Prepared by: \*\*Ajaykumar Nishad\*\*

For: \*\*Junior Data Scientist – Trader Behavior Insights\*\*

## GitHub Repository: [https://github.com/ajxy1910/trader\\\_behavior\\\_insights.git](https://github.com/ajxy1910/trader\\_behavior\\_insights.git)

