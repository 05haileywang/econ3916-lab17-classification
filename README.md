# econ3916-lab17-classification

# Classification: When 90% Accurate Is Worthless

## Objective

The goal of this lab was to understand how logistic regression works for classification and why accuracy isn't always the best way to evaluate a model, especially when one outcome is much more common than another.

## Methodology

- Used a dataset of 6,000 simulated loan applications with a default rate of 9.6%.
- Trained a logistic regression model to predict whether applicants would default on their loans.
- Compared the model's accuracy to a baseline that predicts nobody will default.
- Interpreted the model's coefficients using log-odds and odds ratios.
- Compared precision and recall at six different thresholds.
- Calculated the costs of false positives and false negatives to find the cheapest threshold.
- Wrote a function called `precision_recall_at()` to calculate precision and recall at different thresholds.

## Key Findings

The model had an accuracy of 90.4% at the default threshold of 0.5, which was the same as the baseline that predicted nobody would default. The model also predicted zero defaults, showing that high accuracy doesn't necessarily mean the model is useful.

I also learned that odds ratios can have different effects on predicted probabilities depending on the starting probability. For example, an odds ratio of about 1.63 for one additional prior default leads to different probability changes at different starting points.

The cost-minimizing threshold was 0.121, which was very close to the closed-form threshold of 0.118. At the lower threshold, the expected cost was about $944 per applicant, compared to $1,147 at the default threshold of 0.5. At the closed-form threshold, precision was 0.181 and recall was 0.477.

## Conclusion

Overall, this lab showed me that accuracy alone can be misleading when working with imbalanced datasets. I think precision, recall, and the costs of different errors are important to consider when evaluating a classification model. Choosing a threshold based on costs rather than automatically using 0.5 can make the model more useful for real-world decisions.
