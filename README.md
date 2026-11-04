Customer Segmentation Analysis Using RFM Model

1. Project Overview

This project analyzes household purchasing behavior using the Recency, Frequency, and Monetary (RFM) model to identify different customer segments and support data-driven marketing strategies.

Using the Dunnhumby – The Complete Journey dataset, this analysis evaluates 2,500 households based on their purchasing recency, transaction frequency, and total purchase value.

The main objective is to identify high-value, loyal, and less-active households, understand their contribution to overall purchase value, and develop targeted business recommendations for each segment.

2. Business Objectives

The main objectives of this project are:

- Identify and classify households based on their purchasing behavior.
- Measure Recency, Frequency, and Monetary for each household.
- Identify high-value and less-active customer segments.
- Evaluate each segment's contribution to total purchase value.
- Develop targeted marketing recommendations based on RFM characteristics.

3. Dataset

Dataset: Dunnhumby – The Complete Journey

The dataset contains retail transaction records describing household purchasing behavior.

Key Attributes

Column| Description
"household_key"| Unique household identifier
"BASKET_ID"| Unique transaction or basket identifier
"DAY"| Sequential day index of the transaction
"PRODUCT_ID"| Unique product identifier
"SALES_VALUE"| Recorded purchase value
"QUANTITY"| Number of units purchased
"STORE_ID"| Store identifier

Dataset Overview

Metric| Value
Total transaction records| 2,595,732
Unique households| 2,500
Unique baskets| 276,484
Unique products| 92,339
Unique stores| 582
Observation period| Day 1–711

The unit of analysis in this project is the household rather than an individual customer.

4. Tools and Technologies

The following tools and libraries were used:

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Google Colab

5. Data Preparation

Data preparation included the following steps:

- Inspecting data types and missing values.
- Checking duplicate records.
- Validating transaction consistency across household, basket, day, and store identifiers.
- Examining zero-value sales and quantity records.
- Aggregating transaction records at the basket and household levels.

For the RFM calculation, only baskets with a positive total "SALES_VALUE" were retained as qualifying purchasing activity.

This resulted in 275,542 qualifying baskets, representing all 2,500 households.

Zero-value baskets were excluded from the RFM calculation to focus on purchasing activity that generated recorded sales value. The original dataset was not modified.

6. RFM Analysis

The RFM model evaluates household purchasing behavior using three metrics.

Metric| Definition| Interpretation
Recency| Reference day minus the last purchase day| Lower values indicate more recent purchases
Frequency| Number of unique qualifying baskets| Higher values indicate more frequent transactions
Monetary| Sum of qualifying "SALES_VALUE"| Higher values indicate greater purchase value

The reference day was set to Day 712, one day after the maximum observed transaction day (Day 711).

RFM Scoring

Each RFM metric was divided into five quantile-based scores.

- Recency was scored in reverse order: lower Recency received a higher score.
- Frequency was scored in ascending order: higher Frequency received a higher score.
- Monetary was scored in ascending order: higher Monetary received a higher score.

Each metric received a score ranging from 1 to 5.

7. Customer Segmentation

Households were classified into eight segments using rule-based RFM scoring.

Segment Distribution

Segment| Household Count| Percentage
Hibernating| 551| 22.04%
Champions| 535| 21.40%
Need Attention| 460| 18.40%
Potential Loyalists| 310| 12.40%
At Risk| 268| 10.72%
Loyal Customers| 266| 10.64%
Big Spenders| 76| 3.04%
Recent Low-Frequency| 34| 1.36%
Total| 2,500| 100.00%

The segmentation rules were designed to produce mutually exclusive categories. Households that did not meet the criteria for the seven defined behavioral segments were assigned to the Need Attention category.

8. Key Findings

8.1 Champions Generate the Largest Purchase Value

Champions account for 21.40% of households but contribute approximately 47.9% of total Monetary value.

This highlights the importance of retaining high-value households.

8.2 Hibernating Is the Largest Segment

Hibernating represents 22.04% of all households, making it the largest segment.

Its relatively low RFM scores indicate lower purchasing activity and purchase value compared with other segments.

8.3 At Risk Represents a Re-engagement Opportunity

At Risk households contribute approximately 12.5% of total Monetary value.

Despite having relatively high historical purchasing frequency and value, their most recent purchasing activity occurred further in the past.

8.4 Loyal Customers Contribute Significantly to Purchase Value

Loyal Customers account for 10.64% of households and contribute approximately 14.1% of total Monetary value.

Their relatively high transaction frequency makes them an important segment for retention strategies.

8.5 Big Spenders Have High Purchase Value per Household

Big Spenders demonstrate high Monetary scores despite having relatively lower Frequency scores.

This suggests an opportunity to encourage more frequent purchases through targeted offers and product bundling.

9. Data Visualizations

The project includes four main visualizations:

1. Customer Segment Distribution — compares the number and percentage of households across segments.
2. RFM Segment Profile — compares median Recency, Frequency, and Monetary values for each segment.
3. Monetary Contribution by Segment — evaluates each segment's contribution to total purchase value.
4. RFM Score Heatmap — compares average RFM scores across customer segments.

10. Business Recommendations

Based on the RFM analysis, the following strategies are recommended:

Segment| Recommended Strategy
Champions| Exclusive rewards, VIP programs, and personalized offers
Loyal Customers| Loyalty points and repeat-purchase incentives
Potential Loyalists| Personalized offers and product recommendations
At Risk| Targeted win-back campaigns
Big Spenders| Premium bundles and cross-selling strategies
Hibernating| Re-engagement campaigns
Recent Low-Frequency| Purchase incentives and complementary product recommendations
Need Attention| Further behavioral evaluation and targeted marketing

These recommendations are proposed strategies based on observed RFM characteristics. Their effectiveness should be evaluated using campaign performance data or controlled experiments.

11. Conclusion

The RFM model provides a structured approach to understanding household purchasing behavior and identifying differences in customer value and activity.

This analysis successfully classified 2,500 households into eight mutually exclusive segments.

The findings indicate that Champions contribute the largest share of total purchase value, while Hibernating represents the largest household segment. At Risk households also represent an important opportunity for targeted re-engagement strategies.

Overall, this project demonstrates how transaction data can be transformed into actionable customer segmentation insights to support retail marketing and customer retention decisions.

12. Limitations

This analysis has several limitations:

- The analysis uses household-level data rather than individual customer-level data.
- Recency is based on a sequential day index, not calendar dates.
- The RFM model reflects purchasing behavior within the observation period and does not establish actual customer churn.
- Monetary represents recorded purchase value, not profit or customer lifetime value.
- The rule-based segmentation reflects selected business criteria and is not a universal customer classification standard.
- The effectiveness of the proposed marketing recommendations has not been experimentally validated.

13. Project Scope

This project focuses specifically on RFM-based household segmentation.

It does not include clustering algorithms, predictive churn modeling, or marketing campaign effectiveness evaluation.