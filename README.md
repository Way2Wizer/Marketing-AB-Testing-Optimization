Marketing A/B Testing & Ad Spend Optimization

📌 The Business Problem
A company launched a new digital marketing campaign. The objective was to determine if the advertisements were successfully driving conversions, and if so, how much of that success could be attributed to the ads. Furthermore, the marketing team needed to know exactly when to show ads to maximize Return on Investment (ROI). Thus, I designed an end-to-end A/B testing framework to statistically prove the true impact of the ads and used machine learning to optimize the delivery schedule.

📊 The Data
The analysis was performed on a dataset of 588,101 unique users, divided into two groups:
1. Treatment Group (Ad): 564,577 users who were exposed to the new advertisement.
2. Control Group (PSA): 23,524 users who were shown a generic Public Service Announcement (baseline).

🛠️ Methodology & Tools
Tools Used: Python (Pandas, NumPy, SciPy, Statsmodels, Matplotlib).
Sanity Checks: Removed duplicate user id entries and utilized a Chi-Square test to ensure the traffic distribution across days and hours was randomized properly.
Primary Hypothesis Testing (Z-Test): Applied a Two-Proportion Z-Test to determine if the difference in conversion rates between the Ad and PSA groups was statistically significant.
Robustness Check (Bootstrapping): Simulated the experiment 5,000 times using random sampling with replacement to validate the stability of the primary hypothesis.
Interaction Effects (ANOVA): Used Analysis of Variance (ANOVA) to determine if the day of the week significantly altered the effectiveness of the advertisements.
Predictive Modeling (Logistic Regression): Trained a logistic regression model to predict the exact probability of a user converting at every hour of the day (0-23).

📈 Key Findings & Results
Overall Campaign Success:
1. Ad Group Conversion Rate: 2.55%
2. PSA Group Conversion Rate: 1.78%\

Statistical Significance: The Z-Test yielded a p-value of 0.0000 (supported by 5,000 bootstrap simulations), proving the ads caused a statistically significant increase in sales.
Business Lift: The campaign generated a relative lift of 43.25%. For every 100,000 users exposed to the ad, the campaign generates roughly 770 extra conversions compared to the baseline.

Day of Week Insights (ANOVA):
The ads perform significantly better early in the week (Monday, Tuesday, Wednesday) and mid-week (Friday, Saturday).
On Thursdays and Sundays, the gap between the Ad group and PSA group shrinks to the point of non-significance.

Hourly Optimization (Logistic Regression):
Conversion probabilities spike drastically in the afternoon (14:00 - 16:00) and again in the evening (20:00 - 21:00).
Late-night and early-morning hours (01:00 - 04:00) yield the lowest expected returns.

💡 Final Business Recommendations
To maximize ROI, the marketing budget should not be distributed evenly.
Scale the Campaign: The ads are mathematically proven to work. Scale the budget generally.
Optimize Daily Spend: Shift ad spend away from Thursdays and Sundays. Allocate the bulk of the budget to Monday through Wednesday.
Optimize Hourly Bidding: Implement dayparting (ad scheduling) to aggressively bid for ad placements during the high-intent windows of 2:00 PM - 4:00 PM and 8:00 PM - 9:00 PM, while turning off or lowering bids for overnight hours.

📁 Files in this Repository
1. Marketing_AB_Test_Analysis.ipynb: The complete Python code and statistical analysis.
2. marketing_AB.csv: The dataset used for the experiment.
