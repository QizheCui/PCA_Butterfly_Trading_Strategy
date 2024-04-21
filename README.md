# PCA Trading Strategy

This project forms the assessment for MATH70121 - Topics in Derivative Pricing 2023-2024. The content draws from lecture notes, including but not limited to **Topic 4: Building Libor/OIS Rate Curves**, **Topic 8: Measuring the Value in IR Instruments**, and **Topic 10: Static Curve RV**. Within this project, we initially gather GBP OIS data across various tenors from 2022 to 2024, construct daily curves using different interpolation schemes, and conduct PCA on the initial 6 months of curve changes. Subsequently, we devise a butterfly trade grounded in curvature, which remains unaffected by both level and slope, and scrutinize the PnL time series. We extend our gratitude to [FinancePy](https://github.com/piterbarg/FinancePy) for providing the essential functionalities for this project.


## FinancePy Installation Guide
To get started with FinancePy, follow these simple steps:

1. Clone the FinancePy repository into a folder on your computer using the following command:
```
git clone https://github.com/piterbarg/FinancePy.git
```

2. Navigate to the FinancePy directory in your terminal using the `cd` command:
```
cd FinancePy
```

3. Run the following command to install FinancePy and set up everything required:
```
python setup.py install
```

After completing these steps, you can import FinancePy as a module for this coursework.

## Overview
- `Curve_Building_Libor.ipynb`: This notebook converts Bloomberg data to benchmark tenors daily, performs curve interpolation based on benchmark instruments employing various schemes, and stores the fitted curve for each day in the `curves.pkl` dictionary. Additionally, it saves the interpolated swap yield across different tenors for each day in `df_yield.pkl`.
- `PCA_Trade_Libor_5s10s20s_changes.ipynb`: This notebook encompasses the following implementations:
    - PCA analysis on the first 6 months of yield changes data, exploring correlations among the first three principal components concerning level, slope, and curvature across diverse tenors.
    - Construct of a butterfly trade utilizing 5s10s20s spot IborSwap, then calcualte DV01, carry&rolls.
    - Calculation of daily PnL and examination of its relationship with the principal components post-trade.
- `gbp_ois_data_cw.xlsx`: Raw Excel data of GBP OIS spanning from 2022 to 2024.


## Contributors
- Ethan Qizhe Cui (CID: 01954652)
- Kelvin Wu (CID: 01955564)
- Ahmed Reda Seghrouchni (CID: 02278403)