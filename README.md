
# 🛡️ Compound Wallet Risk Scoring System
# https://colab.research.google.com/drive/1Ac8Z2sHvyiInirouDNDKbJR0Dav0JEcu#scrollTo=ebb647e5
## 📘 Overview
This project analyzes transaction behavior of wallets interacting with the **Compound V2/V3 protocol** and assigns a **risk score between 0 and 1000** based on lending/borrowing activity. It also includes **machine learning-based clustering** to identify behavioral risk patterns among users.


## 📂 Project Structure

.
├── compound_risk_scoring.ipynb # Jupyter notebook with all code and markdown explanations
├── Compound_Risk_Scores.csv # Output CSV with wallet_id and score
├── Compound_Risk_Score_Documentation.pdf # Project documentation
└── README.md # This file



## ⚙️ Setup Instructions

### 1. Clone Repository
```bash
git clone https://github.com/yourusername/compound-risk-scoring.git
cd compound-risk-scoring
2. Install Required Libraries
Use Google Colab (recommended), or install locally:

pip install requests pandas matplotlib seaborn scikit-learn
🧮 Steps Performed
1. Data Collection
Fetched on-chain transaction data from Compound API for each wallet.

Transactions included: Supply, Borrow, Repay, Withdraw.

2. Feature Engineering
Calculated key features:

total_supply_amount

total_borrow_amount

repayment_ratio = total_repay / total_borrow

utilization_ratio = total_borrow / total_supply

num_transactions

3. Normalization
Used Min-Max normalization to scale all features between 0 and 1.

4. Risk Scoring Logic
Risk Score = weighted combination of features:

High utilization and low repayment → Higher risk

High supply and frequent activity → Lower risk

Final score scaled between 0–1000.

5. Machine Learning Enhancement
Applied KMeans Clustering on normalized features.

Helps group similar wallets (e.g., risky vs. safe).

Clustering can assist in anomaly detection or future classification models.

6. Visualization
Plotted risk score distributions.

Identified top 10 high-risk and low-risk wallets.

📊 Output
📄 CSV File:
wallet_id	score
0xfaa0768bde629806739c3a4620656c5d26f44ef2	732
0x...	...

📌 Risk Score Range
0 (High Risk) → Very poor repayment, high borrow-to-supply ratio

1000 (Low Risk) → Responsible lending behavior, low utilization

💡 Why Use Machine Learning?
Clustering reveals hidden wallet behavior patterns.

Can help:

Validate scoring logic.

Group users into risk categories (e.g., low, medium, high).

Extend into fraud/anomaly detection or real-time alerts.

🚀 Future Enhancements
Integrate real-time risk scoring API.

Incorporate on-chain credit scoring models.

Include wallet-specific collateral asset evaluation.

Add graph-based wallet interactions (DeFi ecosystem).

👨‍💻 Author
Meruva Peddababu

🧠 Focus: AI, DeFi, and Risk Modeling
