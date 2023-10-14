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
    - `daysFromDateEntryStart`
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
    - `basicMonthlySalary - monthlyExpenses`
    - `positive basicMonthlySalary - monthlyExpenses`
    - `monthlyFamilyIncome - monthlyExpenses`
    - `positive monthlyFamilyIncome - monthlyExpenses`
    - `basicMonthlySalary / monthlyFamilyIncome`
    - `monthlyExpenses / basicMonthlySalary`
    - `monthlyExpenses / monthlyFamilyIncome`
    - `monthlyVices / basicMonthlySalary`
    - `monthlyVices / monthlyFamilyIncome`
    - `basicMonthlySalary / workingFamilyCount`
    - `basicMonthlySalary / residentsCount`
    - `monthlyFamilyIncome / workingFamilyCount`
    - `monthlyFamilyIncome / residentsCount`
    - `monthlyExpenses / workingFamilyCount`
    - `monthlyExpenses / residentsCount`
    - `monthlyUtilityBills / workingFamilyCount`
    - `monthlyUtilityBills / residentsCount`
2. List of Preprocessing Steps

# | Preprocessing Steps | Choices |
|---|---|---|
1 | `basicMonthlySalary` < 100  is multiplied by 1,000 | Yes; No
2 | Remove those with the same values over many features | Yes; No
3 | Filter out 0 `positiveMonthlySoloNetIncome` | Yes; No
4 | Filter out 0 `positiveMonthlyFamilyNetIncome` | Yes; No
5 | Filter out 0 `positiveMonthlySoloNetIncomeWithSavings` | Yes; No
6 | Filter out 0 `positiveMonthlyFamilyNetIncomeWithSavings` | Yes; No
7 | Filter out 0 `positive monthlyFamilyIncome - basicMonthlySalary` | Yes; No
8 | Filter out 0 `positive basicMonthlySalary - monthlyExpenses` | Yes; No
9 | Filter out 0 `positive monthlyFamilyIncome - monthlyExpenses` | Yes; No
10 | Include `monthlyExpenses / basicMonthlySalary` | Yes; No
11 | Include `monthlyVices / basicMonthlySalary` | Yes; No
12 | Include `basicMonthlySalary / workingFamilyCount` | Yes; No
13 | Include `basicMonthlySalary / residentsCount` | Yes; No
14 | Include `monthlyFamilyIncome / workingFamilyCount` | Yes; No
15 | Include `monthlyFamilyIncome / residentsCount` | Yes; No
16 | Include `monthlyExpenses / workingFamilyCount` | Yes; No
17 | Include `monthlyExpenses / residentsCount` | Yes; No
18 | Include `monthlyUtilityBills / workingFamilyCount` | Yes; No
19 | Include `monthlyUtilityBills / residentsCount` | Yes; No
20 | Bin `basicMonthlySalary` | Yes; No
21 | Bin `monthlyFamilyIncome` | Yes; No
22 | Bin `positiveMonthlySoloNetIncome` | Yes; No
23 | Bin `positiveMonthlyFamilyNetIncome` | Yes; No
24 | Bin `positiveMonthlySoloNetIncomeWithSavings` | Yes; No
25 | Bin `positiveMonthlyFamilyNetIncomeWithSavings` | Yes; No
26 | Bin `totalMonthlyExpenses` | Yes; No
27 | Bin `totalMonthlyVices` | Yes; No
28 | Bin `totalNetWorth` | Yes; No
29 | Outlier removal (Need to generate different set of outliers for different combos of above steps)| Yes; No
30 | OHE of categorical variables | Yes; No
31 | Variance Thresholding| None; Threshold == 0.05; Threshold == 0.10; Threshold == 0.15
32 | Removal of multicollinearity among the features| None; via `df.corr()`; via VIF
33 | Dimensionality reduction | None; PCA; SVD; t-SNE; UMAP

32 | Scaling | None; StandardScaler(); RobustScaler(); MinMaxScaler()
33 | Resampling | RandomOverSampler, RandomUnderSampler, SMOTE, SMOTE-NC