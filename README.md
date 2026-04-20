# us-customer-data-statistical-analysis
Unlocking Customer Insights: A Statistical Investigation
A Python-based end-to-end statistical analysis of a retail company's customer dataset

📋 Project Overview
A mid-sized retail company had collected data on 10,675 customers across 10 US states but was making marketing and strategy decisions based on untested demographic assumptions.
This project conducts a full statistical investigation — from raw data loading through hypothesis testing — to validate those assumptions with actual data and convert findings into clear, actionable business recommendations.

❗ Problem Statement
The company assumed:

Gender drives monthly spending
Education level influences how much customers spend
Older customers are less active/engaged
Customer spending varies significantly by state

None of these assumptions had been statistically tested.
Without validation, the company risked running misdirected campaigns, wasting marketing budgets, and missing genuine engagement opportunities.

🎯 Objective

Understand and clean the dataset for reliable analysis
Compute and interpret descriptive statistics
Visualize distributions, relationships, and group-level patterns
Conduct bivariate analysis to explore variable relationships
Formulate and statistically test business hypotheses
Deliver clear business insights and strategic recommendations

Tools & Libraries

Python 3 — Core programming language
Pandas — Data loading, cleaning, manipulation
NumPy — Numerical operations
Matplotlib & Seaborn — Data visualization (9 plots)
SciPy — Hypothesis testing (T-Test, ANOVA, Pearson Correlation)
Jupyter Notebook — Analysis environment


📊 Project Workflow
Step 1 — Data Understanding

Loaded the dataset and inspected the first 5 records
Identified shape: 10,675 rows × 12 columns
Fixed incorrect data types: JoinDate and TransactionDate converted from object to datetime64
Confirmed: 0 missing values, 0 duplicate records
Found 1,000 unique CustomerIDs with repeat transactions in the dataset

Step 2 — Descriptive Statistics

Computed mean, median, standard deviation for numerical columns
Key findings:

Average age: ~49 years (middle-aged customer base)
Mean MonthlySpend: ~$332, Median: ~$282 → positive skew; a small group are high spenders
Mean DaysSinceLastInteraction: 538 days → majority of customers are disengaged



Step 3 — Data Visualization
Built 9 plots to explore distributions and relationships:

Histogram — Age distribution
Boxplot — Age (no outliers detected)
Histogram — MonthlySpend (right-skewed)
Boxplot — MonthlySpend (significant high-spend outliers identified)
Bar chart — Gender distribution (near-equal split)
Bar chart — Education level distribution (broadly even)
Bar chart — State distribution (California and Florida slightly higher)
Scatter plot — Age vs MonthlySpend, coloured by Education (no clear pattern)
KDE plot — MonthlySpend by Marital Status (near-identical distributions)

Step 4 — Bivariate Analysis

Correlation matrix: All numerical variables show near-zero correlation → No strong linear relationships
Crosstab: Gender × Marital Status → Balanced distribution across all groups
Group averages: Spend by State, Education, and Gender → Differences exist but are marginal

Step 5 — Hypothesis Formulation
Four business hypotheses were formally defined prior to testing:

Male and female customers spend differently
Education level affects average monthly spend
Older customers are less active (more days since last interaction)
Monthly spend varies significantly across states

Step 6 — Hypothesis Testing (α = 0.05)
Gender vs Spend (Independent T-Test)
p-value = 0.734 → No significant difference in spending based on gender
Education vs Spend (One-Way ANOVA)
p-value = 0.922 → Education level has no significant impact on spending
Age vs Activity (Pearson Correlation)
r = -0.004, p-value = 0.682 → No significant relationship between age and activity
State vs Spend (One-Way ANOVA)
p-value = 0.346 → No significant variation in spending across states
🔍 Key Insight

All tested variables were statistically insignificant at the 5% significance level, indicating that demographic factors did not meaningfully influence customer spending or activity in this dataset.

Step 7 — Business Insights & Recommendations
Education Spend Gap (Negligible)
Insight: Master’s holders spend slightly more, but the difference is not statistically significant
Recommendation: Focus on behavioral segmentation (e.g., recency, frequency) instead of education-based targeting
Marital Status vs Spend (0.43% Difference)
Insight: Marital status does not meaningfully influence spending behavior
Recommendation: Avoid building campaigns around marital status
Arizona — High Variability (std = 243.71)
Insight: Customer behavior is highly diverse and less predictable
Recommendation: Use personalized and segmented marketing campaigns
Colorado — Low Variability (std = 211.54)
Insight: Spending behavior is stable and predictable
Recommendation: Standardized campaigns can be applied effectively
Customer Inactivity (Avg. 538 Days Since Last Interaction)
Insight: A significant portion of customers are disengaged or at risk of churn
Recommendation: Implement a tiered reactivation strategy based on inactivity duration
🔍 Key Takeaway

Demographic factors provide limited actionable value. Behavioral patterns and engagement metrics offer stronger signals for driving targeted marketing strategies and improving customer retention.

Tiered Engagement Strategy Recommended:

Active (< 90 days): Reward with loyalty perks and personalized offers
Semi-active (1–2 years): Send targeted reminder emails and promotional incentives
Dormant (3+ years): Launch win-back campaigns or deprioritize in marketing spend


💡 Key Takeaways

Statistical testing prevents expensive mistakes. This company would have wasted budget targeting by gender, education, and location — none of which significantly affect spending.
The real risk is engagement drop-off. With an average of 538 days since last interaction, the company's biggest challenge is retention, not acquisition.
Demographic assumptions rarely survive contact with data. Behavioural variables (recency, frequency, spend patterns) are far stronger predictors than demographics alone.
