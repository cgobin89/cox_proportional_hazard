This repository contains my script to run a multivariate Cox proportional hazard (Cox PH) model w/ clinical features and protein expression as predictors to assess laryngeal cancer patient survival risk.
** This script is for demonstration purposes only as access to my real patient dataset is excluded **

Packages:
• panadas
• numpy
• matplotlib
• lifelines
• shap

Features:
• OS_Months:	Survival duration (months); float
• OS_Status:	Death event indicator (1 = event, 0 = censored); integer
• Age:	Age at baseline (float)
• Sex:	0 = female, 1 = male; integer
• Race: 0 = White, 1 = Black; integer
• Treatment:	0 = Tx naive; 1 = Tx received; integer
• ABCC1: 0 = low H scores < 100; 1 = high H scores >= 100; integer
• Grade: 0 = well differentiated; 1 = moderately/poorly differentiated; integer
• MRN: Patient ID used for labeling in risk score table; string

Outputs:
• Cox PH summary: hazard ratios, confidence intervals, and p-values for each feature assessed individually while holding the other features constant in the model
• Patient-level risk score and median risk score calculation with subsequent stratification into low versus high-risk groups if respectively <= or > median risk score
• C-index: quantifies predictive ability of cox Ph model in discriminating between low and high-risk patients
• -log2(p) of log-likelihood ratio test values > 4.32 indicate overall model significance, informing how well the set of predictors fits the observed survival times
• Nomograms and SHAP plots: visually demonstrate the direction of the feature value in relation to its contribution to predicted risk
• Kaplan-Meier plots: visually demonstrate survival by predicted risk groups and individual features; includes log-rank p values to indicate significance between survival curves
• Scatter plots: visually demonstrate individual patients by risk scores and feature values
• Risk score table: outputs patient IDs, feature values, risk scores and risk category
