# Supervised ML

### 1. Least Squares
- Tries to fit a line such that the sum of square of the residuals on the training data is the minimum
- Generally, overfits the training data with high variance
- `metric = sum(square of all residuals)`

### 2. Ridge Regression
- Introduces a penalty term to the **least squares** that adds a little **bias** to the overall metric
	- Has a little introductory bias that significantly reduces the model variance
- This helps to prevent overfitting as it decreases the slope sensitivity of the fitted line
- `metric = sum(square of all residuals) + lambda * square of slope` 
	- `lambda` is an arbitraty value that is generally calculated experimentally using cross-validation. The value of lambda that generates the minimum residual error is chosen
- Ridge regression can also be applied with Logistic Regression, where it optimizes the **sum of the likelihoods** instead of the **squared residuals** => `metric = sum of likelihoods + lambda * square(slope)`
- When the sample sizes are relatively small, then **Ridge Regression** can improve predictions made from new data (i.e. reduce **Variance**) by making the predictions less sensitive to the training data

### 3. Lasso Regression
- Very similar to the **Ridge Regression** but with a few major differences
- Instead of squaring the **slope** in the ridge regression term, Lasso uses the absolute value of the slope.
	- `metric = sum(square of all residuals) + lambda * abs(slope)`
- Both ridge and lasso regression make the model less sensitive to the training data size
- The big difference between **Ridge** and **Lasso** regression is that Ridge regression can only shrink the slope asymptotically close to 0 while Lasso regression can shrink the slope all the way to 0
	- Hence, **Lasso Regression** is better at removing insignificant features from the dataset that have less influence to the predicted outcome
- In summary, Ridge regression tends to do a little better than Lasso regression when most of the features in the dataset are useful. But **Lasso** is preferrable in cases where there can be useless variables in the model's equation