# Goals
There are three important factors in underwriting credit: 
1. Past credit history (which is what we don’t have for college students)
2. Capacity ( this is the ability to pay back the loan that is received ) **
3. Collateral (because these are college students they will not be putting up collateral because their loans are not this large) 

We are focusing on Capacity — their ability to pay back the loan 
* This will depend on the individuals debt to income ratio
* This is where behavior risk analysis will come into play // assessing the risk of the likeliness to default

## Our Model 
To predict capacity, we used data from WSJ and U.S. College Scorecard, which gave us access to data on an undergraduate's college, region of the U.S. the college is siutated in, their major, average student loan debt, and SAT/ACT scores. We used this data to train a linear regression and random forest model to predict an undergraduate's mean annual income 1 - 5 years out of college. The linear regressor failed miserably as it could not capture the nonlinearities present in the data. However, the random forest actually did quite well, achieving accuracies well over 90% after we binned the income into discrete ranges. After creating the models, we also tested the model rigorously from hand-drawn examples and found that engineering students at MIT and Stanford commanded the highest salaries after college, which is expected and communication majors from Black Hills State University had the lowest salaries. After scaling the salary by both the major taken and college, we came to a mean absolute error (MAE) of $3239, which is quite good since it means our model was only off by average of 3239 dollars for its predictions. To improve our model, the next steps we can take consist of removing redundant features using PCA, tuning our hyperparameters using GridSearch or a genetic algorithm, and stacking multiple models together to create an ensemble model.

## Next Steps
Our end goal is to create a Risk-Assessment Model (RAM) that uses an individual's predicted debt-to-income ratio to determine the likelihood of defaulting on their loans / what interest rate should the set to assess this risk. To estimate this, we we will have to take a look at other data in addition to earnings potential such as campus involvement, work experience, GPA, and bank account information. Currently, data on past loans and previous missed payments is available through LendingClub -- how often an individual missed payments, how long it takes an individual to make missed payments, what his/her overall repayment rate was, etc. If we can combine this information and integrate it with the currently developed model, we can eventually create the RAM.

