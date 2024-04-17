# PCA trading strategy

This project is part of the assessment of MATH70121 - Topics in Derivative Pricing 2023-2024. The material is based on materials covered in lecture notes include not limited to **Topic 4: Building Libor/OIS Rate Curves**, **Topic 8: Measuring the Value in IR Instruments**, **Topic 10: Static Curve RV**. In this project, we first obtain the GBP OIS data across different tenors between 2022 and 2024, build curves for each day using various interpolaion scheme, and perform PCA on the first 6 months of curve changes. We then construct a butterfly trade based on the curvature that is immune to both level and slope, and investigate the PnL time series. Special thanks to [FinancePy](https://github.com/piterbarg/FinancePy) for providing various functionalities needed for this project. 
## Overview
- `Curve_Building_Libor.ipynb`: This file first convert Bloomberg data to benchmark tenors for each day, then interpolate the curve based on benchmark instruments with various scheme. Finally it stored in the fitted curve for every day in the dictionary `curves.pkl` and the interpolated swap yield across different tenors fir every day in `df_yield.pkl`.
- `PCA_Trade_Libor_5s10s20s_changes.ipynb`: This file contains implementation of below:
    - Perform PCA on first 6m of the data on changes in yield, and explore correlation among the first three principle components against level, slope, curvature across different tenors
    - Construct a butterfly trade using 5s10s20s spot IborSwap.
    - Calculate daily PnL and investigate it's relationship with the principle components post trade.
- `gbp_ois_data_cw.xlsx`: Raw Excel data of GBP OIS between 2022 and 2024.

## Contributors
- Ethan Qizhe Cui (CID: 01954652)
- Kelvin Wu (CID: 01955564)
- Ahmed Reda Seghrouchni (CID: 02278403)