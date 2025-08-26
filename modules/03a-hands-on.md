# Fitting hazard models in R

Prepare a reproducible report (.md or html output format) using quarto or rmarkdown.

## Q1. 

Consider a [cohort of cancer patients (link)](https://tgstewart.cloud/age-stage-survival.parquet). To better understand the disease, physicians want to learn how survival varies by age and stage. The dataset has three variables: age, stage, and days between diagnosis and death. 

Using the data, fit the following models using maximum likelihood. Model the outcome with covariates age and stage. 

1. A single Weibull baseline hazard with a common age relationship across stage. 
1. A single Weibull baseline hazard with a stage specific age relationship.
1. Parametric baseline hazard stratified by stage, a common age relationship.
1. Parametric baseline hazard stratified by stage, a stage-specific age relationship.
1. (Optional) Mean of log days with stage-specific age relationship. 

For each model,  

1. Write a mathematical expression of the model
1. Generate a partial effect plot of log relative hazard by age, stratified by stage. (Uncertainty interval not required for now.)
1. Generate a partial effect plot of median survival by age, stratified by stage. (Uncertainty interval not required for now.)
There is no reason to think the log relative hazard is linear in age. 

I recommend that you use Stan via the Rstan package. 

## Q2

For each observation in the dataset, generate a random draws from the outcome distribution implied by the model in 4. With the new data, refit the model.  Compare the original and new parameter estimates.

## Q3

Generate a visualization which compares the distributions of the observed outcomes to the simulated outcomes. 