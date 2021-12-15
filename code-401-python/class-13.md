# Linear Regressions

[Source: bigdata-madesimple](https://bigdata-madesimple.com/how-to-run-linear-regression-in-python-scikit-learn/)

[Scikit-learn](https://scikit-learn.org/stable/) is a Python module for machine learning. It can be used for regression, classification, clustering, model selection, and dimensionality reduction.

In linear regressions, Y represents the depending variable and X represents the independent variable(s).

`from sklearn.linear_model import LinearRegression` is required to use the scikit-learn linear regression functions.

Important functions:

* `lm.fit()` - fits a linear model
* `lm.predict()` - Predict Y using the linear model with estimated coefficients.
* `lm.score()` - Returns the coefficient of determination (R^2)
* `lm.coef_`&`lm.intercept_` - give the coefficients and estimated intercepts of a model.

Normally a regression won't be performed on an entire data set. Data should be split into **training** and **test** sets. This allows us to find a model based on fit to training data, then test it against real data to see how well it predicts outcomes.

Division of data for training and tests **must be done randomly** to prevent bias in the model.

**Residual plots** can be used to visualize errors in data. In a residual plot, data should be scattered around line zero without structure. If the data appears to show structure, the model missed something and should be revised.
