# Findings

## Part 1: Data Exploration

Findings
- There is a strong positive correlation between interest rates and bad loans
- There is also an inverse relationship between loan grade and the frequency of bad loans
- There doesn't appear to be a strong relationship between loan amount and loan status
- Loans originating at the beginning of the financial crisis in 07/08 fared significantly worse than those originating in recent years
- Individuals with higher incomes are less likely to have bad loans than those with lower incomes
- Loans taken out for education or for small businesses go bad at significantly higher rates than those for other purposes
- Individual loans are more likely to go bad than joint ones

## Part 2: Business Analysis

Assumptions 
- To identify the loans with at least 36 months of history available, I calculated the number of months between the loan issue date and the most recent issue date in the dataset. This assumes that a) all loan histories have been kept up-to-date and b) loan histories are updated on a monthly basis.

Conclusions 
- The 36 month term loans with at least 36 months of history available averaged a 2.9 percent annual rate of return (8.9 percent overall)
- The 2012 grade-G loans had the highest annual rate of return of any cohort with an average annual return rate of 7.1 percent. 

## Part 3: Modeling
All three models were effective. They performed significantly better than both the average loan and a random sample of loans, with the random forest model performing best and the linear regression model performing least well. For small sample sizes (e.g. 100-200) the random forest and decision tree models performed nearly 3 times as well as an average loan (between 8.5 and 10.6 percent per year versus 2.9 percent). The linear regression model, on the other hand, performed only slightly better than both the average loan and a random sample of loans for small samples, but about 1.5x better for sample sizes approaching 1000. For large sample sizes (e.g. 5000), the random forest and decision tree models were more than 2x as good as an average loan, returning 6 percent or more per year, while the linear regression was 1.5x as good as an average loan, returning ~4.5 percent per year. 

While the random forest model performed best, it does not meet either criteria of simple or business friendly. The linear regression and decision tree models, on the other hand, are intuitive and simple enough to be used in a business setting. Both model ran quickly enough (~10 seconds each) on a local machine to work well even with larger datasets. 

