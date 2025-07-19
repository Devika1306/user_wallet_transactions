The credit scores range from **0 to 1000**, binned into intervals of 100 for analysis:
| Score Range | Wallet Count |
|-------------|--------------|
| 0–100       | 4            |
| 101–200     | 6            |
| 201–300     | 0            |
| 301–1000    | 0            |

Score Range Histogram

| Range    | █ Count |
| -------- | ------- |
| 0–100    | ████    |
| 101–200  | ██████  |
| 201–1000 |         |

 Behavior Insights:

Wallets Scoring **0–100**:
- Engage in minimal or non-diverse activity.
- Low repay-to-borrow ratio.
- May include bots or inactive accounts.
- Often show signs of risky usage or high liquidation ratios.

 Wallets Scoring **101–200**:
- Show signs of responsible usage, e.g., some `repay` behavior.
- Fewer liquidations, and occasional use of `redeemUnderlying`.
- Likely newer or small-scale participants still building a healthy profile.

Notes on Scoring Logic

The credit scoring algorithm considered:
- Total deposits and borrowings.
- Repay ratio: `repay_amount / borrow_amount`
- Liquidation count and frequency.
- Diversity of transaction types.

A weighted formula normalized the final score to a 0–1000 scale.

 Future Work

- Add more wallets to get a more complete distribution.
- Tune feature importance based on actual repayment/loss metrics.
- Use clustering or supervised labels if available to train a predictive model.

