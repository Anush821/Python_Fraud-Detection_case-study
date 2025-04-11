# 📌 Project Title: Rule-Based Financial Transaction Fraud Detection
Rule-Based Financial Transaction Fraud Detection
# 🧠 Objective:
To identify potential fraudulent transactions using simple yet effective rule-based logic, followed by evaluating performance with visual analysis and confusion matrix.
# 📂 Dataset:
• **Dataset Used**: PaySim Synthetic Financial Transactions Dataset

• **Records**: ~6.3 million transactions

• **Key Fields**: amount, type, isFraud, oldbalanceOrg, newbalanceOrig
# ⚙️ Approach:
## 1. Data Exploration & Preprocessing:

• Checked distribution of transaction types and amounts.

• Found a heavy skew: most transaction amounts are small, with few large outliers.

• Fraudulent transactions were mostly concentrated in 'TRANSFER' and 'CASH_OUT' types.

## 2. Defined Rule-Based Logic:
    df['isSuspicious'] = (
        (df['type'].isin(['TRANSFER', 'CASH_OUT'])) &
        (df['amount'] > 200000)
    ).astype(int)

• Chose a threshold based on distribution and fraud concentration.

• This logic assumes high-value transfers/cash-outs are likely suspicious.
## 3. Evaluated Rule Performance:
• Used confusion_matrix from sklearn to compare predictions vs actual frauds.

• Visualized true positives, false positives, etc.
## 4. Visual Insights:
• Created a bar chart showing:

    • Total frauds

    • Frauds caught by the rule

    • Missed frauds
• Helped communicate the rule’s effectiveness and its limitations.

# 📊 Results:
| Metric	       |       Value    |
|----------------|----------------|
|Total Frauds	   |    e.g., 8213  |
|Frauds Detected |	    e.g., 4652|
|Frauds Missed	 |      e.g., 3561|
|Precision (Rule)|	 ~95% (varies)|
|Recall (Rule)	 |  ~56% (varies) |

_**“Rule-based approach caught a significant portion of actual frauds with high precision, but missed some — highlighting the need for deeper techniques like ML in future versions.”**_

# ✅ Key Takeaways:
• Rule-based detection is a good starting point for fraud analytics, especially in domains where explainability matters.

• This project helped me explore how simple logic can be evaluated with visual and statistical validation.

• It also built a foundation for scaling to machine learning-based fraud detection in the next iteration.
