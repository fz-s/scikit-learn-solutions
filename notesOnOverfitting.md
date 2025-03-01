what is an Overfitted model?
A model that performs very well on the training data, but poorly on the test data.

Preventing Overfitting
1. regularization = a technique to penalize complex models that are over-fitted
    - Add a penalty to the objective function (which is to minimize the loss / least square error)
    - The penalty will be a function of the regression coefficients. So, higher/complex the regression coefficients, higher the penalty. The model will strive to minimize the penalty, thus avoiding complex fit.
    - Regularization reduces variance error, but increases bias

    Techniques:
    - Lasso Regression = Penalizes large regression coefficients using L1-Norm (sum of modulus of regression coefficients raised to the power of 1)
    - Ridge Regression = Penalizes large regression coefficients using L2-Norm (sum of modulus of regression coefficients raised to the power of 2)
    - Elastic Net Regression = Combines lasso and ridge regression 
2. cross validation = employing distinct training, validation and test phases 
3. dropout (for NNs) = intertionally turning-off few neurons during training