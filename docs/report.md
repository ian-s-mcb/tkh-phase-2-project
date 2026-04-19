# tkh-phase-2-project - Financial Fraud Detection - Report

1. Which insights did you gain from your EDA?

  Our EDA phase confirmed how small our minority class was. Of the 6.4
  million transactions in the dataset, only 8,213 were fraudulent, which amounts
  to 0.129%. This phase also revealed which columns needed encoding or string
  replacements, like the `type` column and the account name columns. Finally,
  the plots in this phase, revealed that the `step` column was mostly uniformly
  distributed noise and that several of our column had collinearity.

2. How did you determine which columns to drop or keep? If your EDA informed
   this process, explain which insights you used to determine which columns were
   not needed.

  We determined that three columns needed to be dropped on the basis of the data
  dictionary. They were `is_flgged_fraud`, `name_orig`, and `name_dest`. The
  first of the three was described a derivative of `amount` column, which we
  already planned on using, and the last two were just identifiers for bank
  accounts. Additionally, we determined that two other columns needed to be
  dropped because of the bivariate analysis that showed collinearity. Those
  columns were `old_balance_orig` and`old_balance_dest`.

3. Which hyperparameter tuning strategy did you use? Grid-search or
   random-search? Why?

  We used the random-search hyperparameter tuning strategy. The reason for this
  choice was runtime performance. Our dataset was bigger than any other we had
  worked with and the type of model we chose, Random Forests, is rather
  computationally expensive. Although grid-search could have found better
  hyperparameters, random-search was much more feasible and was able to be run
  over the course of one night.

4. How did your model's performance change after discovering optimal
   hyperparameters?

  After discovering optimal hyperparameters, our model's performance improved
  from a precision of 0.76 to 0.83, a recall of 0.56 to 0.65, and f1-score of
  0.65 to 0.73, each for the '1' / fraud class.

5. What was your final F1 Score?

  Our final f1-score was 0.73.
