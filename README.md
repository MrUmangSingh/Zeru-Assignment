# Zeru-Assignment

This project assigns a **credit score between 0 and 1000** to each DeFi wallet based on its historical transaction behavior. The score aims to quantify how trustworthy and responsible a wallet is, based on how it interacts with decentralized finance protocols.

---

## Features Engineered

From the raw transaction JSON, we extract the following features:

- total_amount: Total deposited amount
- avg_amount: Average deposit amount
- max_amount: Largest single deposit
- tx_count: Number of deposit transactions
- tx_per_day: Transaction frequency
- variance: Variance in time between deposits (stability)
- unique_assets: Asset diversification
- network_diversity: Chain/network diversification

---

## Scoring Methodology

1. Log-scaling of skewed features (like amount & variance)
2. Sub-scores calculated for:
   - Volume
   - Frequency
   - Stability
   - Diversification
   - Network usage
3. Clipping outliers between 5th–95th percentiles
4. MinMax scaling of sub-scores
5. Weighted sum of sub-scores to compute raw score
6. Final credit score = raw_score × 1000

---

## Outputs

- `analysis.md`: Written insights about score distribution and wallet behavior
- `score_distribution.png`: Graph showing how wallets are distributed across score ranges
- Final wallet scores with structure:
