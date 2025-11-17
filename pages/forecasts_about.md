---
layout: page
title: "About the model"
hide: true
---


## A Statistical Model to make Probabilistic Forecasts of September Arctic Sea Ice Extent

**About the model:** We train a transfer operator to predict the internal variability of September Arctic sea ice extent. A transfer operator is a statistical model that calculates the probability of a given output state based on the value of the input state (Sevellec and Drijfhout, 2018). The transfer operator used for this outlook predicts September SIE (output state) from July 2024 SIE (input state) for a 5 year lag time and moving mean. 

**Building the model:** We apply the following steps to build the transfer operator: (i) bin the input and output metrics (July and September SIE) into a number of states; (ii) count the number of input states, Ni; (iii) for each input state, count the number of trajectories in each output state, ni,j; (iv) calculate the probability of transitioning from the ith state to the jth state as pi = ni,j/Ni. Figure 1 shows a summary schematic for this transfer operator.

**Model Inputs:** The total variations in sea ice extent are decomposed into a forced contribution and a residual (internal variability). Variations in sea ice extent are largely described by the internal variability. The model inputs and outputs are in the form of residuals, standardized to zero mean and unit standard deviation. The model is trained using output from ten different CMIP6 models and tested using observations from the NSIDC Monthly Sea Ice Index.

**The Data:**

*Training:* For the training phase we use sea ice extent from the historical runs of ten different models in CMIP6 (models listed below), where the residual is calculated as the difference between each ensemble member and the respective model ensemble mean (the forced contribution). CMIP6 models used to train the transfer operator (Model name [number of members in brackets]): ACCESS-CM2[10], ACCESS-ESM1-5[40], CanESM5 [25], IPSL-CM6A[33], MIROC6[50], MRI-ESM2-0[10].

*Testing:* The outlook prediction is made using a separate testing data set, where the input is the sea ice extent calculated from observations (NSIDC Monthly Sea Ice Index). Here, the forced contribution is different for the 1979-2014 and 2015-2024 period. The forced component is taken to be the weighted mean of the CMIP6 ensemble means from historical (1979-2014) and SSP5-8.5 (2015-2024) simulations, where the weights are based on the number of ensemble members used for each model. 

**References**

Fetterer, F., Knowles, K., Meier, W. N., Savoie, M. & Windnagel, A. K. (2017). Sea Ice Index, Version 3 [Data Set]. Boulder, Colorado USA. National Snow and Ice Data Center. https://doi.org/10.7265/N5K072F8. Date Accessed 07-11-2024.

Notz, D., Jahn, A., Holland, M., Hunke, E., Massonnet, F., Stroeve, J., Tremblay, B., and Vancoppenolle, M.: The CMIP6 Sea-Ice Model Intercomparison Project (SIMIP): understanding sea ice through climate-model simulations, Geosci. Model Dev., 9, 3427–3446, https://doi.org/10.5194/gmd-9-3427-2016, 2016.

Sévellec, F., Drijfhout, S.S. A novel probabilistic forecast system predicting anomalously warm 2018-2022 reinforcing the long-term global warming trend. Nat Commun 9, 3024 (2018). https://doi.org/10.1038/s41467-018-05442-8
