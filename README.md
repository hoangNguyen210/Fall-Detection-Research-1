# Fall Detection using multimodal data
> Falling is one of the most common dangers that the elderly usually face during their daily lives, and the potential of death after falling might increase if they live alone.  As reported by the Center for Diseases and Controls [CDC](https://www.cdc.gov/homeandrecreationalsafety/falls/adultfalls.html), the percentage of death after falling in the U.S went up 30% from 2007 to 2016 for older adults. In case we do not find an appropriate way to stop these rates keep growing, there may be approximately seven deaths per hour by 2030.

## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Dataset description](#features)
* 
<!-- * [Screenshots](#screenshots)
* [Setup](#setup)
* [Usage](#usage)
* [Project Status](#project-status) -->

* [Room for Improvement](#room-for-improvement)
* [Acknowledgements](#acknowledgements)
* [Contact](#contact)
<!-- * [License](#license) -->

## Project Status
Project is:  _complete_. And accepted to present at [MMM 2022 Conference](https://mmm2022.org/).

## General Information
- Understanding the fearful outcomes that falling leads to, developing a fall
detection system is essential than ever before.
- We going to use [UP-Fall Detection](https://www.mdpi.com/1424-8220/19/9/1988) in this project and utilize both machine learning and deep learning on this data.
- Enable to detect a precise fall detection system might significantly mitigate the risk of falling in the ederly
<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


## Technologies Used
- numpy - version 1.0
- pandas - version 2.0
- tensorflow - version 3.0
- keras - version 
- sklearn - 

## Dataset description
- You can download UP-Fall Detection dataset in this [link](https://sites.google.com/up.edu.mx/har-up/) . This dataset includes over 850 GB of data from wearable sensors, ambient sensors, and vision equipment. 17 young healthy people with age ranging from 18–24 years old were invited to perform 11 different activities. Here is the summary of activities. 

| Activity ID | Description  | Duration (s)  |
| :-----:     | :-:          | :-:           |
|     1        | Falling forward using hands          | 10           |
| 2     | Falling forward using knees          | 10           |
| 3    | Falling backwards         | 10           |
| 4     | Falling sideward          | 10           |
| 5     | Falling sitting in empty chair         | 10           |
| 6     | Walking          | 60           |
| 7     | Standing         | 60           |
| 8     | Sitting          | 60           |
| 9     | Picking up an object         | 10           |
| 10     | Jumping          | 30           |
| 11     | Laying          | 60           |

|![Location of measure device](./img/location.png)|
|:--:| 
| *Location of measurement devices* |
<!-- If you have screenshots you'd like to share, include them here. -->
You can read more about this dataset at this [paper](https://www.mdpi.com/1424-8220/19/9/1988).

## Setup
- numpy - version 1.0
- pandas - version 2.0
- tensorflow - version 3.0
- keras - version 
- sklearn - 

## Data preprocessing :
- Related to the sensor data, we dropped all duplicate records and removed rows and columns having missing values. We also utilized the index of sensor data to query to vision-based dataset to gurantee 2 kind of datasets have same samples, this step is significant to combine these datasets in when compiling the models.
- In addition, we also applied Standard Scaler and scaling each by divide 255 to warrant our dataset in small range. 

## Proposed methods :
- In term of sensor dataset, we proposed 2 machine learning algorithm that win a lot of Kaggle competitions : [XGBoost](https://xgboost.readthedocs.io/en/stable/), [CatBoost](https://catboost.ai/) and 1 deep learning technique : MLP. Here is some hyperparameters we choose for these algorithms : 

| Models | Hyperparameters  | 
| :-----:     | :-:          |
|     XGBoost        | objective="multi:softprob", <br> learning rate = 0.5, <br> random state = 42,  <br> use label encoder = False, <br> # of estimators = 100 <br>|
| CatBoost     | # of estimators = 500, <br>  random seed = 42, <br> learning rate = 0.25,  <br>      max depth = 12  <br>      | 


|![Location of measure device](./img/SENSOR.png)|
|:--:| 
| *MLP model for sensor data* |

- With camera based dataset, we take advantages of CNN2D. 

|![Location of measure device](./img/CAMERA.png)|
|:--:| 
| *CNN2D model for camera data* |

- Concatenating both kind of data :

|![Location of measure device](./img/C1+C2.png)|
|:--:| 
| *Concatenaing CNN2D Model for Camera 1 and Camera 2* |

|![Location of measure device](./img/S+C1+C2.png)|
|:--:| 
| *Combining Sensor , Camera 1 and Camera 2* |



## Result 

<!-- | Data | Model  | Accuracy  | Precision | Recall | F1-Score |
|---------------|-----------|-----------|--------|----------|
| S | XGBoost <br> CatBoost <br> MLP  |  | 99.21 <br> 99.05 <br> 99.04 <br> | 99.19 <br> 99.02 <br> 99.05 <br> | 99.21 <br> 99.05 <br> 99.03 <br>| 99.20 <br> 99.02 <br> 99.03 <br> | -->


| Data | Model  | Accuracy  | Precision | Recall | F1-Score
| :-----:     | :-:          | :-:           |  :-:           |  :-:           |  :-:           |
|     S        | XGBoost <br> CatBoost <br> MLP <br> | 99.21 <br> 99.05   <br>  99.04 <br>     | 99.19 <br> 99.02 <br>  99.05 <br>         | 99.21 <br> 99.05 <br> 99.03 <br> |99.20 <br> 99.02 <br> 99.03 <br> |




## Room for Improvement
Include areas you believe need improvement / could be improved. Also add TODOs for future development.

Room for improvement:
- Improvement to be done 1
- Improvement to be done 2

To do:
- Feature to be added 1
- Feature to be added 2


## Acknowledgements
Give credit here.
- This project was inspired by...
- This project was based on [this tutorial](https://www.example.com).
- Many thanks to...


## Contact
Created by [@flynerdpl](https://www.flynerd.pl/) - feel free to contact me!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->
