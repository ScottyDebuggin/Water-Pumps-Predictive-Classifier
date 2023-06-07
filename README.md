# Project Title: Pump It Up: Taarifa Tanzania Water Pump Challenge
## 1. Project Overview:
### Introduction
### Objectives
##### The main objective was to identify key predictive features, and build/fine-tune a machine learning model to predict whether a water pump is functional or broken.
## 2. Data Preparation
### Data Acquisition
##### The datasets were pulled from [DrivenData Competition Page](https://www.drivendata.org/competitions/7/pump-it-up-data-mining-the-water-table/page/24/), they were obtained directly from the Taarifa and the Tanzanian Ministry of Water.
### Columns Info
###### -amount_tsh: Represents the total static head, indicating the volume of water available at the waterpoint.
###### -date_recorded: The entry date for the corresponding row of data.
###### -funder: Identifies the entity responsible for funding the well's establishment.
###### -gps_height: Denotes the well's altitude, as determined by GPS.
###### -installer: Specifies the organization that carried out the well's installation.
###### -longitude and latitude: GPS coordinates pinpointing the well's location.
###### -wpt_name: The designated name of the waterpoint, if any.
###### -num_private: Indicates whether the well is for private use.
###### -basin: The water basin where the well is located.
###### -'subvillage', 'region', 'region_code', 'district_code', 'lga', 'ward': Detailed geographical identifiers for the well's location.
###### -population: The number of individuals residing in close proximity to the well.
###### -public_meeting: A Boolean variable indicating whether a public meeting occurred.
###### -recorded_by: The organization or group responsible for the data entry in this row.
###### -'scheme_management' and 'scheme_name': The operating authority for the waterpoint.
###### -permit: A Boolean variable denoting whether the waterpoint has received the necessary authorization.
###### -construction_year: The year in which the waterpoint was constructed.
###### -'extraction_type', 'extraction_type_group', 'extraction_type_class': The method employed by the waterpoint to extract water.
###### -'management' and 'management_group': Describes the management system overseeing the waterpoint's operations.
###### -'payment' and 'payment_type': Specifies the cost associated with the water from the waterpoint.
###### -'water_quality' and 'quality_group': An assessment of the water's quality from the waterpoint.
###### -'quantity' and 'quantity_group': The measure of water quantity available at the waterpoint.
###### -'source', 'source_type', 'source_class': The origin of the water supplied by the waterpoint.
###### -'waterpoint_type' and 'waterpoint_type_group': The category or type of the waterpoint.
### Data Cleaning
##### The initial data was cleaned to handle missing values, outliers, and any irrelevant information. This involved techniques such as imputation, dropping irrelevant columns, standardizing values, and changing datatypes.
### Exploratory Data Analysis (EDA)
##### A descriptive analysis was performed to better understand the data, its structure, and key summary statistics.
### Data Transformation
##### Data transformation was done to convert categorical data into a format that can be used for machine learning models. This involved one-hot encoding and ordinal encoding 
## 4. Feature Engineering
### Derived Features
#####  New numerical features were derived from patterns in the existing features to help improve the model's performance.
### Feature_importance_
##### I coded a block to print the most relevant features from the data, although because I decided on building a Decision Tree model, I didn't manually select important features for ensembling.
## 5. Model Development
### Decision Tree (DT)
##### A Decision Tree model was built as the base model to predict the operational status of water pumps. The data was noisy and the model was likely overfit, so I also built a SMOTE model to adjust re-sampling size of the (DT).
### XGBoost
##### In addition, an XGBoost model was trained for the same purpose. XGBoost is known for its speed and model performance, and my model blew the (DT) model out of the water, resulting in 91% accuracy!
## 6. Evaluation and Results
### Performance Metrics
##### The performance of the models was evaluated using accuracy, precision, recall, F1 score, ROC-AUC curve, and a confusion matrix for visualization.
##### For the purpose of this project, I'd assume falsely classifying a 'broken' pump as 'functional' would be more harmful, because these water pumps are relied on by the local population for clean water on a daily basis.
## 7. Conclusions
### Key Takeaways
##### There are many factors that affect a water pumps functionability, but some main features are:

###### -pump height above water level
###### -population count using the pump
###### -whether or not the pump operates through dry seasons
###### -whether or not the pump was installed according to regulated standards
###### -age of the pump, since construction
###### -quality of water flowing through the pump

##### These insights would prove useful to anybody planning the construction of new pumps in the future, to increase efficiency and prolong the pump lifespan. 
### Future Work
##### For upcoming improvements to this project, I would add a 3rd predictive class 'functional-but-needs-repair' based on the highlighted important features. I would then tune an XGBoost model to accurately predict water pump class, according to the competition rules at [DrivenData](https://www.drivendata.org/competitions/7/pump-it-up-data-mining-the-water-table/rules/)

##### Also I would like to print more interesting visuals, and add some to this README file
