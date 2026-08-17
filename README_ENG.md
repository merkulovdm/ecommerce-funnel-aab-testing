# E-Commerce Funnel Analysis & A/A/B Testing

Identifying conversion drop-off points across the user journey and validating experiment group homogeneity before A/B testing.

## Business Context

An e-commerce platform needed to understand where users abandon the purchase funnel and whether a proposed UI change meaningfully improved conversion. Before measuring the experiment effect, the integrity of the randomisation had to be verified via an A/A test.

## Key Results

| Funnel step | Conversion |
|---|---|
| View → Cart | 28.5% |
| Cart → Purchase | 34.9% |
| **View → Purchase (end-to-end)** | **~10%** |

- **A/A test:** no statistically significant difference between control groups (p = 0.059) — randomisation confirmed valid
- **A/B test:** the experimental UI variant produced no significant lift in purchase conversion (p > 0.05)
- The largest drop-off occurs at the `view → cart` stage, accounting for ~70% of lost users

## Recommendations

1. **Priority — view → cart:** improve product cards, surface ratings/reviews, revisit pricing perception
2. **Secondary — cart → purchase:** simplify checkout, add payment options, remove mandatory registration

## Methodology

- Funnel analysis (unique users per step, step-over-step and top-of-funnel conversion)
- A/A/B experiment design with random user-level group assignment
- Two-proportion z-test (implemented via `scipy.stats.norm`, no external dependencies)
- Period: Q1 2025 (full quarter, uniform group coverage)

## Tech Stack

`Python` · `pandas` · `numpy` · `scipy` · `matplotlib` · `seaborn`

## How to Run

1. Place `ecommerce_dataset1.zip` in the project root
2. Open `ecommerce_funnel_ab_test.ipynb` in Jupyter
3. Run all cells — no additional setup required

## Project Structure

```
├── ecommerce_funnel_ab_test.ipynb   # Main analysis notebook
├── ecommerce_dataset1.zip           # Raw data (events, orders, users, products)
└── README.md
```
