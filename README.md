# Code and procedures for the ICIS 2023 article: "Should we use Interactions? It Depends! Predictive Validation of Interaction Terms in PLS-SEM"
# Danks & Ray (2023)

## Procedure for generating point predictions from PLS-SEM models including a non-linear term generated using the *product indicator* approach.

1. Identify training ($x_{is}$) and holdout ($x_{oos}$) sets of cases. 
- Here holdout data can be new data or data that has been partitioned during cross validation. 
2. Estimate parameters of PLS-SEM model using training data ($x_{is}$) only and applying the product indicators approach for generating the non-linear term. 
- Retain both initial descriptive statistics of the training data mean ($m_{is}$) and standard deviation ($s_{is}$), and
- Estimated measurement weights ($w_{is}$) and loadings ($l_{is}$), and structural path coefficients ($B_{is}$). 
3. Generate the holdout ($x_{oos}$) product indicator data for the non-linear term. 
- Standardize holdout data using training standard deviation $s_{is}$ and mean $m_{is}$.
- Generate the preliminary holdout product indicators data by all possible pairwise products of the indicators of the exogenous variables ($x_i$) and of the moderator variable ($m_j$) using holdout data ($x_{oos}$). 
- Append the holdout data from step 1 with the new manufactured indicators from step 3.
4. Standardize holdout data from step 3 using training standard deviation $s_{is}$ and mean $m_{is}$.
5. Predict exogenous construct scores from outer weights: 
- Predict the construct scores of exogenous constructs using holdout data from step 5 and the training measurement weights ($w_{is}$):
$$X = x.w_{is}$$
6. Predict the endogenous construct scores:
- Multiply the predicted construct scores ($X$) by structural paths ($B_{is}$):
$$Y = X.B$$
7. Predict the indicator scores of endogenous constructs:
- Multiply the predicted construct scores ($Y$) with the measurement loadings ($l_{is}$):
$$y=Y.l_{is}$$
8. Unstandardize predictions. 
- Use the training data standard deviation $s_{is}$ and mean $m_{is}$ to bring the predictions back to the original scale. Multiply each predicted observation by its corresponding standard deviation and add its corresponding mean.


## Procedure for generating point predictions from PLS-SEM models including a non-linear term generated using the orthogonal approach.

1. Identify training ($x_{is}$) and holdout $x_{oos}$) sets of cases. 
- Here holdout data can be new data or data that has been partitioned during cross validation.
2. Estimate parameters of PLS-SEM model using training data ($x_{is}$) only and applying the product indicators approach for generating the non-linear term.
- Retain both initial descriptive statistics of the training data mean ($m_{is}$) and standard deviation ($s_{is}$), and 
- Estimated measurement weights ($w_{is}$) and loadings ($l_{is}$), and structural path coefficients ($B_{is}$). 
- In addition to the measurement and structural model estimates, the parameter estimates for the linear models used in the residual centering ($b_{is}$) need to be retained. 
3. Generate the holdout product indicator data for the non-linear term. 
- Standardize holdout data using training standard deviation ($s_{is}$) and mean ($m_{is}$).
- Generate the preliminary holdout product indicators data by all possible pairwise products of the indicators of the exogenous variables ($x_i$) and of the moderator variable ($m_j$) using holdout data ($x_{oos}$). 
4. Residual center the holdout data for indicators of the non-linear term
- For each of the preliminary indicators of the non-linear term (from 3) use the parameter estimates of the relevant residual centering linear model ($b_{is}$) and the holdout data ($x_{oos}$) to generate a predicted score for the preliminary indicator.
- Deduct the predicted holdout preliminary indicator scores calculated in step 4. from the preliminary holdout product indicator scores from step 3. 
- Append the holdout data from step 1 with the new residual centered indicators from step 4.
5. Standardize holdout data from step 4 using training standard deviation $s_{is}$ and mean $m_{is}$.
6. Predict exogenous construct scores from outer weights: 
- Predict the construct scores of exogenous constructs using holdout data from step 5 and the training measurement weights ($w_{is}$):
$$ X = x.w_{is}$$
7. Predict the endogenous construct scores:
- Multiply the predicted construct scores ($X$) by structural paths ($B_{is}$):
$$Y = X.B$$
8. Predict the indicator scores of endogenous constructs:
- Multiply the predicted construct scores ($Y$) with the measurement loadings ($l_{is}$):
$$y=Y.l_{is}$$
9. Unstandardize predictions. 
- Use the training data standard deviation $s_{is}$ and mean $m_{is}$ to bring the predictions back to the original scale. Multiply each predicted observation by its corresponding standard deviation and add its corresponding mean.
