This project assigns a credit score (0–1000) to each wallet based on its historical transaction behavior on the Aave V2 protocol. A higher score reflects responsible, human-like financial usage; a lower score indicates risky, bot-like, or exploitative behavior.

JSON file (user-wallet-transactions.json) containing raw transaction-level data.

Each record includes fields like:
wallet or user: wallet address
action: one of deposit, borrow, repay, redeemunderlying, liquidationcall
actionData: transaction amount
timestamp: time of transaction

Example Heuristic Formula: 
score = 300 + min(repay_ratio, 1.0) * 500 
              + min(deposits + redeems, 10) * 10 
              - (num_liquidations * 100)

Output:
A file wallet_credit_scores.csv mapping wallet addresses to final credit scores.
Score range: 0 (risky) to 1000 (excellent)

Extensibility Ideas:
Use time-decay weighting: recent actions matter more

Add wallet metadata: transaction frequency, asset diversity, flash loan activity

Train a supervised model if labeled good/bad outcomes are available

Add bot-detection rules for precision

