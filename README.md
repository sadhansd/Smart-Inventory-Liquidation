# Smart-Inventory-Liquidation

_Smart Inventory Liquidation: Dynamic Markdown Optimization for Perishable Items in Small Retail Chains_

## Business Problem:
Small and mid-sized grocery retailers often suffer losses due to unsold perishable goods. The challenge is to set the right discount level at the right time before product expiry so that you can maximize sell-through while reducing waste and avoiding excessive profit loss.

## Objective:
Build an AI system that optimizes markdown timing and discount percentage for perishable products to maximize sell-through rate while minimizing waste and margin loss.
- Forecasts near-term demand for perishable products.
- Quantifies uncertainty around how price impacts demand (elasticity).
- Determines the optimal markdown timing and percentage.

## Solution Overview
1. **Demand Forecasting**  
   - Hybrid `SARIMA + LSTM` model for short-term predictions.
2. **Price Elasticity Modeling**  
   - `Bayesian Ridge Regression` to quantify demand sensitivity to discounts.
3. **Causal Inference**  
   - `DoWhy`/`CausalImpact` to isolate markdown effects from external factors.
4. **Prescriptive Optimization**  
   - Recommends optimal discount (%) and timing (hours before expiry).
5. **Explainable AI**
   - `SHAP/LIME` explanations for model decisions.
6. **EDA**
   - `ANOVA` for variation across product types, time, store location


## Hypothesis Testing & Validation
**A/B/C Testing Framework:**  
- **Group A**: No discount  
- **Group B**: 12-hour pre-expiry discount (20%)  
- **Group C**: 6-hour pre-expiry discount (30%)

## Dataset: 
[M5 Forecasting](https://www.kaggle.com/competitions/m5-forecasting-accuracy/data)
### why ?
- It has weekly selling prices per item per store and daily unit sales per item per store. We can observe how changes in price influence demand over time (price elasticity)
- We can quantify how demand responds to price while controlling for:
    Item type
  	Store effects
  	Seasonality
  	Holidays/events

