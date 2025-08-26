# ML1 Final Exam

## Time to event and proportional hazards models

The proportional hazards model simultaneously estimates the cumulative hazard, the survival function, the CDF, and PDF of the time-to-event outcome.

It seamlessly incorporates partially observed outcomes, allowing censored observations to contribute to the estimation of the model.  Censored observations occur frequently in the collection of patient cohort data due to common life events.  For example, in a cohort of prostate cancer patients, a certain percentage will relocate and decide not to continue providing data to the researchers.  Likewise, patients may not seek medical care for several years, making it challenging to pinpoint when newly diagnosed medical conditions developed.

## A recent lament 

A recent letter to the editor lamented that two recent publications ignored partially observed outcomes in the construction of risk prediction models for cancer patients.  The letter writers, *Peng et. al.*, noted that the authors of the risk prediction models, *Karabacak et. al.* and *Li et. al.*, simply excluded participants for whom an outcome status was not fully observed.  For example, in constructing a 5-year survival model, the authors implemented an approach that would have excluded participants who were censored at year 4.5.  *Peng et. al.* noted that "[the construction of the risk prediction models was] undertaken without due consideration for the impact of censored data on the [models'] fidelity."

## Uncalibrated or Inefficient or Neither?

The **impact of censored data** might manifest itself in three ways: (a) bias, (b) inefficiency, or (c) none of the above.  **Bias** refers to predicted probabilities that are poorly calibrated, even in the long run, as the training data increases in the limit.  In the case of a risk prediction model, **bias** is the difference between the predicted probability and the true probability, even as the training data becomes infinite.  If the true risk of death within 5 years is 0.4, then bias refers to a model which predicts a 5 year risk of death at 0.5, even as the model is built on larger and larger datasets.  This type of bias typically results from a systematic, unaccounted imbalance in the data collection or analysis.

**Inefficiency** refers to the relative degree of uncertainty in a prediction, precisely when the sample size is fixed and finite.  Suppose method A and method B both generate predictions about 5-year mortality.  Even if both generate predictions **without** bias, the method which generates the predictions with greater precision is preferred.  Ignoring censored data may not create bias but impact relative inefficiency.  For example, a predicted risk of 0.4 and interval (0.3, 0.5) is much more helpful than a method that estimates 0.4 with interval (0.1, 0.7).  Because tighter intervals correspond to greater precision/efficiency, it may not be appropriate to ignore partially observed outcomes for the sake of simplicity.

## Final exam

### Part 1

For the final exam, you will write a technical report which will either (a) persuade *Karabacak et. al.* and *Li et. al.* that ignoring partially observed outcomes creates bias or reduces efficiency or (b) persuade *Peng et. al.* that ignoring partially observed outcomes does not have the impact that their letter suggests.

You will provide justification for your conclusion with simulation.  If there is nuance to the conclusion, you should provide clear instruction to your audience about when ignoring censoring is OK and when it is problematic.

### Part 2

*Karabacak et. al.* suggested machine learning is more capable than regression approaches for identifying non-linear relationships and interactions between variables, providing more nuanced and intricate insights.  In part 2, you will provide a tutorial for *Karabacak et. al.* on how to capture non-linear relationships and interactions, using regularization as needed.


## Papers 

>Peng, ZH., Huang, ZX., Tian, JH. et al.  The application of time-to-event analysis in machine learning prognostic models. J Transl Med 22, 146 (2024). https://doi.org/10.1186/s12967-024-04909-1


>Karabacak, M., Jagtiani, P., Carrasquilla, A. et al. Prognosis Individualized: Survival predictions for WHO grade II and III gliomas with a machine learning-based web application.  npj Digit.  Med. 6, 200 (2023).  https://doi.org/10.1038/s41746-023-00948-y

>Li, C., Liu, M., Zhang, Y. et al.  Novel models by machine learning to predict prognosis of breast cancer brain metastases. J Transl Med 21, 404 (2023). https://doi.org/10.1186/s12967-023-04277-2
