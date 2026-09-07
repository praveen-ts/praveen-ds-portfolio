# Customer LTV & Multi-Touch Attribution

## Problem
Predicted customer lifetime value and compared attribution models to understand which marketing touchpoints actually drive conversions — a common gap between "last-click" attribution and true multi-touch influence.

## Data
Olist Brazilian e-commerce dataset (real, public) — 96,478 orders with customer, order, payment, and review data.

## Approach
- XGBoost regression model to predict customer LTV
- Compared 6 attribution models, including last-touch, linear, time-decay, and Markov chain removal-effect attribution
- SQL-based feature engineering layer via DuckDB

## Key Results
- LTV model: **R² = 0.41**
- Markov chain removal-effect attribution provided a more defensible view of channel contribution than simple last-touch attribution, by explicitly modeling what conversion rate would look like if a channel were removed entirely

## Limitations (disclosed)
- LTV prediction horizon limited by dataset's observed order history window
- Attribution touchpoint data inferred from available order/payment sequence, not true multi-channel marketing logs (Olist dataset doesn't include ad-click-level data)

## Why this approach
Most attribution reporting defaults to last-click because it's simple, but it systematically undervalues upper-funnel touchpoints. This project demonstrates a more rigorous, causally-motivated alternative (Markov removal-effect) that's increasingly used in production marketing analytics.
