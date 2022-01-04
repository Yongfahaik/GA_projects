# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 2 - Ames Housing Data and Kaggle Challenge
By Yong Fah Aik

### Overview
In this project, we are tasked with creating a regression model based on the Ames Housing Dataset, and this model will be used to predict the price of a house at sale. The Ames Housing Dataset is made up of two datasets: The `train dataset` with all of the columns needed to generate and refine the models, and the `test dataset` with all of those columns except for the target that we are trying to predict in the Regression model. 

For the purpose of this project, it is divided into two notebooks, one for EDA and data-cleaning, another for the analysis and modelling.

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

1. *Key Takeaway*

**Recommendations:** 

*Recommended features*
