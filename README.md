# Analysis-of-Crop-Production-in-India
## PROJECT OVERVIEW
Agriculture is one of those sectors that deal with lots of numbers. And when we have so many types of crops and temperatures they grow properly on, temperatures they don’t give proper yield, the cost of crops in each state of India, duration of each season. So, all these factors mean that there is a huge scope of visualization of data and analysis of the data and give a better idea to this sector through graphs and visualizations about which crops can be used per season, factors affecting certain crops in certain regions, etc. 


So, the aim of this project is to analyze and understand crop production and how it is affected by factors such as temperature, rainfall, air quality, production costs, etc. Several datasets are taken and so many combinations of fields are being taken into consideration for getting a better idea of how crops work in India by Data Visualization. This project does a feature analysis of 4 different datasets which are crops, rainfall, air quality, and temperature. Machine learning models for several algorithms were used to predict crop production from rainfall, air quality, and temperature. 

## DATASET
Four different types of datasets are taken into the picture for this analysis which are Agriculture in India, Rainfall in India, India air quality data, and temperature of India. All the datasets are taken from Kaggle and the links to the datasets will be provided in the references section of the paper. The agriculture dataset has the cost of production, cost of cultivation, yield, the state in which the crop grows. Rainfall in India dataset has district-wise rainfall data for each month, India air quality dataset has statewide SO2, NO2, RSPM, and SPM values. These are the harmful gases that affect the quality of air, and the air is a major factor in the proper growth of a crop. The temperature dataset gives the average temperature of the whole country month-wise. This is the data taken for the feature analysis and Visualization.


## COMPONENTS
The goal of the work is to analyze crop production and its factors such as air quality, temperature, and rainfall. After an individual and combined analysis of each of the factors and crop production, the final step is to create a machine learning model to predict crop production based on all three factors.

The main components of this system are Individual Feature Analysis, Combined Analysis, and Model Development. First, the datasets are considered independent and are analyzed. Then the relationships between each dataset and all others are explored. Finally, the model is trained using the dependent factors affecting crop production.

### Individual Feature Analysis

The Crop Production, Air Quality, Temperature, and Rainfall datasets each have their own set of features that give meaningful insight. So each of them has been explored individually by developing visualizations to understand their behavior independently.

The main aim of these visualizations is to draw some conclusions from the features in the datasets.


### Combined Analysis

In this module, the data is transformed into a suitable format for each dataset and is combined and analyzed. The missing data is also handled in this module as merging data becomes hard because of it.

The missing data can be divided into three parts, beginning, middle, and end. The hardest to handle out of the three is beginning. Here, we cannot use features like front fill and backfill. Front fill means to fill the current data with the first non-null data while backfill means to fill the current data with the first non-null data from the ending.

The front fill cannot be used as in the beginning there is no preceding data while the backfill will spoil the flow, that is if the value is decreasing or increasing it changes the data entirely. Since we cannot interpolate the data as well, the only option was to delete the columns with missing values in the beginning.

For the data in the middle and the end, interpolation can be used and it fills most of the data except some values if there were consecutive missing data that cannot be filled using this method. These values can be filled using front fill or backfill.

The major relationships that are explored are:
SO2 and NO2 Concentration VS Temperature
SO2 and NO2 Concentration VS Rainfall
Crop Production VS SO2 and NO2 VS Rainfall VS Temperature

### Model Development

This is the final module where the machine learning model is developed. First, the data is made into a compatible format when merging the four datasets. The crop type, the year of production needs to be coordinated with the corresponding years in the SO2, NO2, Temperature, and Rainfall.

The next step is to implement the models using the merged dataset. The models need to be supervised learning and regression algorithms. The algorithms selected are:
-Linear Regression
-Ridge Regression
-Lasso Regression
-Support Vector Machine(SVM)
-Decision Tree Regressor 
-Gradient Booster

The methodology for evaluating the metrics is cross-validation with five splits. This has been chosen because the data is small and irregular making it prone to highly varying metrics. This can be overcome in cross-validation as the five metrics will be derived from five models and the mean of the metrics can be used to compare the models.

## ANALYSIS AND DISCUSSION
### Individual Feature Analysis

Analysis for Crop Production Dataset:
This dataset gives various insights into which crop gives more profit, which state has a higher yield, etc.

In image 1, the yields vs cost of cultivation are given and the most noticeable observation is that sugarcane has the highest yield when compared to the cost of cultivation which is the lowest of all the given crops. So one can conclude that sugarcane yields the most profits out of the given crops.

Similarly from image 2, it is easy to conclude that Tamil Nadu has the highest yield which is very high compared to other states.

Images 3,4 and 5 indicate that the mean production of crops is around 180 and it has an outlier far above that value. The same can be said to be the case of yield where the average is around 150 and there is a single outlier at 1200. While the mean area of crops is approximately 125 and there are many outliers.

Analysis for Air Quality Dataset:
This dataset provides information about which states have a high concentration of SO2, NO2, SPM, and RSPM. It also tells us how the air quality changed over the years in the states.

Image 6 conveys that Delhi and Rajasthan have a very high amount of SPM compared to other states while Andaman and Nicobar Islands have a high concentration of RSPM like Delhi, Punjab, and Rajasthan even though its other pollutants have very low concentrations.

Image 7 tells how the pollutants have varied over the years and the conclusion is that none of them have truly increased or decreased. They have just varied over the years at almost a constant rate.

Images 8 and 9 show how the SO2 and NO2 concentrations varied in the states across the years. It can be seen that northeastern states have a very low concentration of pollutants compared to others with southern states following closely.

Analysis for Temperature Dataset:
Image 10 tells how the temperature does not vary much during JAN-FEB and OCT-DEC compared to other quarters. Annually, the mean of the temperatures is around 29.2 degrees celsius.

Analysis for Rainfall Dataset:
Image 11 indicates how the rainfall varied for different subdivisions over the years. While Arunachal Pradesh has a varying rainfall distribution every year, Rajasthan and Karnataka have a constant amount of rainfall compared to other states.

Image 12 shows the distribution of rainfall in each quarter and JUN-SEP seems to have the highest rainfall compared to any other quarter whereas JAN-FEB had the least amount of rainfall for almost all the states.

### Combined Analysis

Image 13 explored the relationship between SO2 and NO2 concentration and Temperature. It is evident that both of them seem to have a direct relationship with each other. When the concentrations of SO2 and NO2 have increased Temperature has also increased and vice-versa.

Image 14 saw how rainfall and pollutant concentration are indirectly proportional to each other. When the concentrations of SO2 and NO2 have decreased, the rainfall has increased in the subsequent year and vice-versa.

Image 15 is a heatmap that tells how crop production and its factors are correlated. The crop production is positively related to temperature and negatively related to rainfall and SO2 and NO2 concentrations.

### Model Development
The objective of this module is to select a suitable model for predicting the crop production value based on the type of the crop, year, temperature, rainfall, SO2, and NO2 concentration.

Images 16 to 21 show algorithms VS metrics so as to identify the best model. By analyzing the above six graphs, Ridge Regression seems to be the best algorithm to implement our model. It has a good variance score as observed in image 16 and it is the only algorithm to have a positive R squared score from image 17.

From images 18 and 21, Ridge regression also has the highest negative mean squared error and negative max error. Even its fit time and score time are in the lower echelons among the models as observed in images 19 and 20.

