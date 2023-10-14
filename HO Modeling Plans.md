# HO Modeling Plans
- Outlier removal
- Variance thresholding
- Removal of highly correlated features
- Feature selection/elimination suggestion by Prof Mich
- Using PCA/SVD/t-SNE/UMAP
- Binning
- Scaling
- Feature creation / derivation
- Creating polynomial features
- Any combination of these

## Preprocessing Step Sets
Preliminaries:
1. Create the following features:
    - `monthlyUtilityBills`
    - `monthlyVices`
    - `monthlyExpenses`
    - `monthlySoloNetIncome`
    - `positiveMonthlySoloNetIncome`
    - `monthlyFamilyNetIncome`
    - `positiveMonthlyFamilyNetIncome`
    - `monthlySoloNetIncomeWithSavings`
    - `positiveMonthlySoloNetIncomeWithSavings`
    - `monthlyFamilyNetIncomeWithSavings`
    - `positiveMonthlyFamilyNetIncomeWithSavings`
    - `monthlyFamilyIncome - basicMonthlySalary`
    - `positive monthlyFamilyIncome - basicMonthlySalary`
    - `basicMonthlySalary - totalMonthlyExpenses`
    - `positive basicMonthlySalary - totalMonthlyExpenses`
    - `monthlyFamilyIncome - totalMonthlyExpenses`
    - `positive monthlyFamilyIncome - totalMonthlyExpenses`
    - `basicMonthlySalary / monthlyFamilyIncome`
    - `monthlyExpenses / basicMonthlySalary`
    - `monthlyExpenses / monthlyFamilyIncome`
    - `monthlyVices / basicMonthlySalary`
    - `basicMonthlySalary / workingFamilyCount`
    - `basicMonthlySalary / residentsCount`
    - `monthlyFamilyIncome / workingFamilyCount`
    - `monthlyFamilyIncome / residentsCount`
    - `monthlyExpenses / workingFamilyCount`
    - `monthlyExpenses / residentsCount`
    - `monthlyUtilityBills / workingFamilyCount`
    - `monthlyUtilityBills / residentsCount`
    - `daysFromDateEntryStart`
2. 

Preprocessing Steps | Choices |
|---|---|
`basicMonthlySalary` < 100  is multiplied by 1,000 | Yes; No
Remove those with the same values over many features | Yes; No
Filter out 0 `positiveMonthlySoloNetIncome` | Yes; No
Filter out 0 `positiveMonthlyFamilyNetIncome` | Yes; No
Filter out 0 `positiveMonthlySoloNetIncomeWithSavings` | Yes; No
Filter out 0 `positiveMonthlyFamilyNetIncomeWithSavings` | Yes; No
Filter out 0 `positive monthlyFamilyIncome - basicMonthlySalary` | Yes; No
Filter out 0 `positive basicMonthlySalary - totalMonthlyExpenses` | Yes; No
Filter out 0 `positive monthlyFamilyIncome - totalMonthlyExpenses` | Yes; No
Bin `basicMonthlySalary` | Yes; No
Bin `basicMonthlySalary` | Yes; No
Bin `monthlyFamilyIncome` | Yes; No
Bin `savings` | Yes; No
Bin `totalMonthlyExpenses` | Yes; No
Bin `totalMonthlyVices` | Yes; No
Bin `totalNetWorth` | Yes; No
Outlier removal (Need to generate different set of outliers for different combos of above steps)| Yes; No
OHE of categorical variables | Yes; No
Variance Thresholding| None; Threshold == 0.05; Threshold == 0.10; Threshold == 0.15
Removal of multicollinearity among the features| None; via `df.corr()`; via VIF
Dimensionality reduction | None; PCA; SVD; t-SNE; UMAP
Scaling | None; StandardScaler(); RobustScaler(); MinMaxScaler()
Resampling | RandomOverSampler, RandomUnderSampler, SMOTE, SMOTE-NC