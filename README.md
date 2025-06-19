# 🧭 Mobile Service Plans Analysis
Telecommunications operator Megaline, offers its customers two prepaid plans, Surf and Ultimate. 
The sales department wants to know which plan generates the most revenue so they can adjust their advertising budget.

---

## 🔍 Project Overview (P-20250505)

Conduct a preliminary rate analysis based on a relatively small customer selection. 
Dataset on 500 Megaline customers: who they are, where they're from, what rate they use, and the number of calls and texts they sent in 2018. 
Objective: Analyze customer behavior and determine which prepaid rate generates the most revenue.

Key questions:

- Customer consumption behaviour
- Which plan, on average, generates the most revenue
- The average revenue of users of the Ultimate and Surf rates differs
- The average revenue of users in the New York-New Jersey area is different from that of users in other regions.

Surf Plan

Monthly payment: $20.
500 minutes per month, 50 text messages, and 15 GB of data.
If package limits are exceeded:
1 minute: 3 cents.
1 text message: 3 cents.
1 GB of data: $10.

Ultimate Plan

Monthly payment: $70.
3,000 minutes per month, 1,000 text messages, and 30 GB of data.
If package limits are exceeded:
1 minute: 1 cent.
1 text message: 1 cent.
1 GB of data: $7.

__Note__: Megaline rounds seconds to minutes and megabytes to gigabytes. For calls, each individual call is rounded up: even if the call lasted only one second, it will still count as a minute. For web traffic, individual web sessions are not rounded up. Instead, the monthly total is rounded up. If someone uses 1025 megabytes this month, they will be charged 2 gigabytes.

---

## 🧮 Data Dictionary

This project has five different tables.

- `megaline_users.csv` (data about users)
    `user_id`: The user's unique identifier.
    `first_name`: The user's first name.
    `last_name`: The user's last name.
    `age`: The user's age (in years).
    `reg_date`: The subscription date (dd, mm, yy).
    `churn_date`: The date the user stopped using the service (if the value is missing, the plan was in use when this database was retrieved).
    `city`: The user's city of residence.
    `plan`: The plan name.

- `megaline_calls.csv` (data about calls):
    `id`: The call's unique identifier.
    `call_date`: The date of the call.
    `duration`: The duration of the call (in minutes).
    `user_id`: The identifier of the user making the call.

- `megaline_messages.csv` (data about SMS):
    `id`: The SMS's unique identifier.
    `message_date`: The date of the SMS.
    `user_id`: The identifier of the user sending the SMS.

- `megaline_internet.csv` (web session data):
    `id`: Unique session identifier.
    `mb_used`: The amount of data used during the session (in megabytes).
    `session_date`: Date of the web session.
    `user_id`: The user identifier.

- `megaline_plans.csv` (tariff data):
    `plan_name`: Tariff name.
    `usd_monthly_fee`: Monthly payment in US dollars.
    `minutes_included`: Minutes included per month.
    `messages_included`: SMS included per month.
    `mb_per_month_included`: Data included per month (in megabytes).
    `usd_per_minute`: Price per minute after exceeding the package limits (for example, if the package includes 100 minutes, the operator will charge for the 101st minute).
    `usd_per_message`: Price per SMS after exceeding the package limits.
    `usd_per_gb`: Price per gigabyte of extra data after exceeding the package limits (1 GB = 1024 megabytes).

---

## 📚 Guided Foundations (Historical Context)

The notebook `00-guided-analysis_foundations.ipynb` reflects an early stage of my data analysis learning journey, guided by TripleTen. It includes data cleaning, basic EDA, and early feature exploration, serving as a foundational block before implementing the improved structure and methodology found in the main analysis.

---

## 📂 Project Structure

```bash
├── data/
│   ├── raw/              # Original dataset(s) in CSV format
│   ├── interim/          # Intermediate cleaned versions
│   └── processed/        # Final, ready-to-analyze dataset
│
├── notebooks/
│   ├── 00-guided-analysis_foundations.ipynb     ← Initial guided project (TripleTen)
│   ├── 01_cleaning.ipynb                        ← Custom cleaning 
│   ├── 02_feature_engineering.ipynb             ← Custom feature engineering
│   ├── 03_eda_and_insights.ipynb                ← Exploratory Data Analysis & visual storytelling
│   └── 04-sda_hypotheses.ipynb                  ← Business insights and hypothesis testing
│
├── src/
│   ├── init.py              # Initialization for reusable functions
│   ├── data_cleaning.py     # Data cleaning and preprocessing functions
│   ├── data_loader.py       # Loader for raw datasets
│   ├── eda.py               # Exploratory data analysis functions
│   ├── features.py          # Creation and transformation functions for new variables to support modeling and EDA
│   └── utils.py             # General utility functions for reusable helpers
│
├── outputs/
│   └── figures/          # Generated plots and visuals
│
├── requirements/
│   └── requirements.txt      # Required Python packages
│
├── .gitignore            # Files and folders to be ignored by Git
└── README.md             # This file
```
---

🛠️ Tools & Libraries

- Python 3.11
- os, pathlib, sys, pandas, NumPy, Matplotlib, seaborn, IPython.display, scipy.stats
- Jupyter Notebook
- Git & GitHub for version control

---

## 📌 Notes

This project is part of a personal learning portfolio focused on developing strong skills in data analysis, statistical thinking, and communication of insights. Constructive feedback is welcome.

---

## 👤 Author   
##### Luis Sergio Pastrana Lemus   
##### Engineer pivoting into Data Science | Passionate about insights, structure, and solving real-world problems with data.   
##### [GitHub Profile](https://github.com/LuisPastranaLemus)   
##### 📍 Querétaro, México     
##### 📧 Contact: luis.pastrana.lemus@engineer.com   
---
