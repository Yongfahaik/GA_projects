# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 2 - Ames Housing Data and Kaggle Challenge
By Yong Fah Aik

### Overview
In this project, we are tasked with creating a regression model based on the Ames Housing Dataset, and this model will be used to predict the price of a house at sale. The Ames Housing Dataset is made up of two datasets: The `train dataset` with all of the columns needed to generate and refine the models, and the `test dataset` with all of those columns except for the target that we are trying to predict in the Regression model. 

For the purpose of this project, it is divided into two notebooks, one for [EDA and data-cleaning](./code/01_EDA_and_Cleaning.ipynb), another for the [analysis and modelling](./code/02_Modelling_and_Recommendations.ipynb).

### Problem Statement
As a consultant to a potential house-owner in the city of Ames of Iowa, I am presented with the challenge of finding the features that will affect the sale price of the house. In doing so, I will then be able to give recommendations to the potential house-owner on the features that will affect the value of the house the most.

---

### Datasets
In this project, we are provided with the Ames Housing data from [Kaggle DSI-US-11 Regression Challenge](https://www.kaggle.com/c/dsi-us-11-project-2-regression-challenge) that is included in the [`datasets`](./datasets/) folder for this project . The data description are also listed [here](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt).

### Data Dictionary
The following 26 features are selected out of the original 80 features that will be used for our modelling process. Do note that some of the features are actually dummy features created from the original data columns.

|Feature|Data Type|Description|
|:--:|:--:|:----------:|
|**lot_frontage**| Continuous | Linear feet of street connected to property |
|**lot_area**| Continuous | Lot size in square feet |
|**overall_qual**| Ordinal | The overall rating of the material and finish of the house |
|**year_built**| Discrete | Original construction date |
|**exter_qual**| Ordinal | The evaluated quality of the material on the exterior |
|**bsmt_qual**| Ordinal | The evaluated height of the basement |
|**bsmt_exposure**| Ordinal | Refers to walkout or garden level walls with split levels or foyers scoring average |
|**total_bsmt_sf**| Continuous | Total square feet of basement area |
|**heating_qc**| Ordinal | Heating quality and condition |
|**gr_liv_area**| Contiuous | Above grade (ground) living area square feet |
|**full_bath**| Discrete | Full bathrooms above grade |
|**kitchen_qual**| Ordinal | Kitchen Quality |
|**totrms_abvgrd**| Discrete | Total rooms above grade (does not include bathrooms) |
|**fireplaces**| Discrete | Number of fireplaces |
|**garage_area**| Continuous | Size of garage in square feet |
|**neighborhood_stonebr**| Dummy (Nominal) | Stone Brook (Physical location within Ames city limits) |
|**neighborhood_nridght**| Dummy (Nominal) | Northridge Heights (Physical location within Ames city limits) |
|**neighborhood_noridge**| Dummy (Nominal) | Northridge (Physical location within Ames city limits) |
|**bsmt_fin_glq**| Dummy (Ordinal) | Rating of basement finished area as Good Living Quarters |
|**garage_builtin**| Dummy (Nominal) | Location of Garage being built-in as part of house |
|**garage_attchd**| Dummy (Nominal) | Location of Garage being attached to home |
|**foundation_pconc**| Dummy (Nominal) | Type of foundation as Poured Concrete |
|**house_1story**| Dummy (Nominal) | One story (Style of dwelling) |
|**house_2story**| Dummy (Nominal) | Two story (Style of dwelling) |
|**masvnr_stone**| Dummy (Nominal) | Masonry veneer type of Stone |
|**masvnr_brkface**| Dummy (Nominal) | Masonry veneer type of Brick Face|
---

### Conclusions and Recommendations

**Key takeaways:** 

The Baseline Model is based on the mean value of `SalePrice` of the training data. After that, Linear Regression, Ridge Regression and Lasso Regression are then modelled on the training data. Finally, additional Polynomial terms are added to the Lasso Model through the addition of interactions terms deemed of note and the use of Polynomial Features. 

For the final model, the entire dataframe of the train dataset is modelled on the Lasso Regression Model with Polynomial Features.

The Metrics of all models are as follows:
|Model|Train/Test **RMSE**| Train/Test **MAE**| Train/Test **R2**|Cross val **RMSE**|Cross val **R2**| No. of Features|
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
|**Baseline**|79526.8522 / 78375.2624| -- | -- | -- | -- | 26 |
|**Linear Regression**| 30818.775 / 26866.9156 | 19916.61 / 19634.45 | 0.8498 / 0.8824 | 32499.3382 | 0.8313 | 26 |
|**Ridge Regression**| 30837.174 / 26679.0112 | 19898.7 / 19612.71 | 0.8496 / 0.8841 | 32500.1995 | 0.8315 | 26 |
|**Lasso Regression**| 30890.5437 / 26499.4763 | 19807.77 / 19494.47 | 0.8491 / 0.8856 | 32413.1619 | 0.8326 | 26 |
|**Lasso Regression (interaction terms)**| 28784.1962 / 25083.6057 | 18938.95 / 18487.04 | 0.869 / 0.8975 | 30763.6683 | 0.8484 | 32 |
|**Lasso Regression (polynominal features)**| 21398.005 / 22423.2328 | 14962.62 / 16136.06 | 0.9276 / 0.9181 | 27024.0471 | 0.8866 | 377 |
|**Lasso Regression (Final)**| 21058.2775 / - | 14806.98 / - | 0.9294 / - | 25192.1239 | 0.898 | 377 |

--

**Recommendations:** 

By looking at the coefficients for the Final Lasso Regression Model with Polynomial Features and the initial Lasso Regression Model, we arrived at the following features with the highest absolute value for their coefficients. Do note that in the case of the former model, only the non-polynomial features are selected.

|Feature|Description|
|:--:|:----------:|
|**lot_area**| Lot size in square feet |
|**overall_qual**| The overall rating of the material and finish of the house |
|**year_built**| Original construction date |
|**gr_liv_area**| Above grade (ground) living area square feet |
|**garage_area**| Size of garage in square feet |
|**neighborhood_stonebr**| Stone Brook (Physical location within Ames city limits) |
|**neighborhood_nridght**| Northridge Heights (Physical location within Ames city limits) |
|**neighborhood_noridge**| Northridge (Physical location within Ames city limits) |
|**house_1story**| One story (Style of dwelling) |

As such, in the recommendation to the potential house-owner, houses that are in either of `three mentioned neighborhoods of Stone Brook, Northridge Heights and Northridge`, and `One story style of houses` will tend to be of a higher price. For `Lot Area`, `Gr Liv Area` and `Garage Area`, the larger the area, the higher the sale price will tend to be. With regards to the `overall quality` rating of the material and finish of the house, the higher the rating, the higher the sale price. And for the `year built`, newer houses would likely be more expensive than older houses. My client would then be able to take this into account when deciding to buy a house.

--

**Conclusions:** 

On the issue of feature engineering, it can be noted from the metrics and coefficients obtained from the models that they can be further refined. The main issue here is that the chosen features are selected based on correlation for the numerical columns and visual plots for the categorical columns, after the columns with too many missing values and the columns with a high proportion of the mode value are dropped. This meant that a lot of features are already dropped prior to the process of modelling.

In the future, perhaps it will be useful to do a quick modelling of the data after a quick data cleaning to drop columns with obvious problems and impute missing data. Then feature engineering can occur to narrow down the features to be selected by analyzing the coefficients of the basic model.

--

Additionally, it should be noted that for the polynomial features added after the feature engineering for additional modeelling, we only did the additions of the few seemingly important features and the use of polynomial features, which is basically a brute-force method. 

In the future, it would be relevant to achieve something in between in the process of refining the model, perhaps a pre-selection of polynomial features that would aid in the modelling process.
