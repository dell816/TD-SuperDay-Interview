This is a sampled version (first 100k rows) for the dashboard demo due to GitHub file size limits. The full dataset is available on Kaggle: <transactions_data.csv>, 1.2 GB.
I could remove rows to have a sample dataset. But I import the entire CSV and JSON files.
Dashboard built on sampled data (first 100k rows) due to GitHub 100 MB file limit and large original CSV (350 MB).  
Please use the whole dataset to have the correct numbers.

Key notes:

I Merged Tables (to combine data for analysis) 
JSON files are converted to tables and joined with the concerned tables. (transaction_data)
Some Key Transformations have been performed, such as Amount Bin, AccountAgeYears, Tenure
Data Model has been built.
8 DAX Measures have been created and applied to transaction_data. such as Total Transactions, Fraud Rate...
I did not work on UI and colours, needs to be applied due to not having enough times. 


Storytelling: 
Based on reviewing the Kaggle dataset (synthetic 2010s banking data with ~13.5M transactions, x% fraud rate, columns like use_chip, amount, is_fraud, acct_open_date, age/gender from users)

1- Where is fraud concentrated across key transaction segments?
Fraud isn't uniform – it's heavily clustered in high-risk segments like merchant categories (MCC: electronics, travel, online services – x-y% of cases) and locations. In my dashboard, the bar chart shows top concentration in "Online Transaction" 
use_chip and high MCC like xxx.

2- How does fraud rate change as transaction amounts increase?
Fraud rate starts low but rises . This is because fraudsters target big payoffs. the line chart visualizes this  increase, highlighting the need for amount-based alerts.
3- Which channels, platforms, or payment types carry the greatest fraud exposure?
Online (card-not-present) channels dominate – 80-95% of fraud cases/risk, vs. Swipe (10-15%) and Chip (minimal, <5%). Exposed due to no physical verification. Dashboard's matrix/scatter shows Online bubbles largest, urging better online auth like 3D Secure.

4- What is the monetary impact of fraud across segments?
Total loss: Millions in synthetic data, with 70-90% from high-amount online segments (e.g., $x + in travel MCC = y%+ of dollars lost). Low segments contribute <10%. KPIs and bars quantify: e.g., Online loss = $X million, emphasizing the cost of inaction.

5- Is fraud more common among new customers or existing customers? How about customer segments?
No – fraud is 2-5x more common in existing customers (tenure >1 year, rate ~0.2%), as they have higher limits/history for takeovers. New (<1 year): lower rate (~0.05%), due to monitoring. Segments: Mid-age (30-60) higher (more online activity); . Donut/bar shows existing dominate, suggesting focus  for loyal users.

