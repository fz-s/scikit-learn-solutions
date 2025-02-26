## Risks in Simple Linear regression (binomial)
- no cause-effect relationship between x & y
- mis-specified relationship - x & y may have a non-linear relationship (ex. polynomial), but we fit a linear model
- incomplete relationship - y is a result of multiple causal variables, but we only fit one

The r_squared metric can be used to diagnose these risks
- no cause-effect relationship --> low r2, also x-y plot will have no patters
- mis-specified relationship --> high r2, residuals are not independent of each other
- incomplete relationship --> low r2, residuals are not independent of x

Mitigating these risks
- no cause-effect relationship --> perform another experiment with different variables and collect observations
- mis-specified relationship --> transform x & y (ex. log)
- incomplete relationship --> perform the same experiment with additional independent variables to add to X


## Risks in Multiple Regression (polynomial)
multi-collinearity: multiple variables containing the same information
- r2 score is not reliable 
    - r2 score will increase with dimensionality, giving the false impression that the model is improving 
    - if this caveat is not known, we might unknowingly fit the model with numerous X variables, resulting in an overfitted model
- the regression coefficients are not reliable in explaining the variance in the underlying data
- the model will perform poorly on out-of-sample data

mitigating multi-collinearity
- understand the data, and eliminate the variables that are closely related
- standardize the data
- use adjusted r2 instead (preferred for evaluating multiple regression)
    - adds a penalty for adding irrelevant variables to the model
- perform dimensionality reduction techniques (ex. Principal Component Analysis)
- if the data contains a categorical variable with k groups, setup (k-1) dummy variables
    - Ex. if you have 1 string variable indicating Male/Female, replace it with a dummy variable with 0 and 1 (1=Male, 0=Female, or vice-versa)

