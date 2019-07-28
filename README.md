# Are we overpaying our employees?
Salary Prediction Based on Job Descriptions

**Author:**
- Hieu Nguyen
- hieu.t.nguyen.aug25@gmail.com

**Project goal:** 
- To predict salary using job description information
- The predicted salary can inform key decision makers when deciding on a prospective employee offer package
- This predicted salary can also help with employee retention as company may lose their best employee to another employer who is willing to pay them more for the same job

**Data:**
- train_features: A csv file containing the features from 1,000,000 job descriptions
- train_salaries: A csv file containing the salaries of those jobs
- test_features: A csv file containing the features from another 1,000,000 job descriptions

**Process:**
- Salary Prediction Project.ipynb
- Part I: Defines
  + The problem
  + Helper functions
- Part II: Discovers
  + There are 5 rows in the train data where salary is zero.
  + The majority of upper-tail outliers in salary are CEO, CFO, CTO, and other senior management
  + The majority of these upper outliers have over 20 years of work experience and over $200K salaries
  + A few Junior level employees also have salaries that are this high
  + They majority of these Junior employees work in Finance and Oil industry with advanced degrees (Doctoral or Master's)
  + Salary is most correlated with Job Type; major and degree are also highly correlated
- Part III: Developes
  + New features
    - Dummy variables for categorical features
    - Dummy features such as: imputed age, advanced degree, executives, etc.
  + One baseline model with MSE = 965
    - Average salaries for each job type was used as the predicted salary for each job
  + Three tuned models 
    - Linear Regression (MSE = 384)
    - Random Forest (MSE = 402)
    - Gradient Boosting (MSE = 357)
- Part IV: Deploys
  + Automated pipeline where the data is loaded, cleaned, trained under 5-fold cross-validation, and the best performing model is selected to predict salaries in the test dataset

**Results:**
- model.txt: saved model, which performed best under 5-fold cross-validation with train data (MSE = 357)
- predictions.csv: saved predictions on test data
