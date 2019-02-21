# Supervised ML

### 1. Least Squares
- Tries to fit a line such that the sum of square of the residuals on the training data is the minimum
- Generally, overfits the training data with high variance
- `metric = sum(square of all residuals)`

### 2. Ridge Regression
- Introduces a penalty term to the **least squares** that adds a little **bias** to the overall metric
- This helps to prevent overfitting as it decreases the slope sensitivity of the fitted line
- `metric = sum(square of all residuals) + lambda * square of slope` 
- `lambda` is an arbitraty value that is generally calculated experimentally using cross-validation. The value of lambda that generates the minimum residual error is chosen
- Ridge regression can also be applied with Logistic Regression, where it optimizes the **sum of the likelihoods** instead of the **squared residuals** => `metric = sum of likelihoods + lambda * square(slope)`
- When the sample sizes are relatively small, then **Ridge Regression** can improve predictions made from new data (i.e. reduce **Variance**) by making the predictions less sensitive to the training data
