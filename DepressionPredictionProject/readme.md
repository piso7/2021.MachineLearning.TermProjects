# Prediction of Depression Using EMA Data => [Full Code](https://github.com/piso7/2021.MachineLearning.TermProjects/blob/main/DepressionPredictionProject/kkw-ml-teamproject_1.ipynb)
<img src="https://user-images.githubusercontent.com/44772344/109740272-5c9b4c80-7c0e-11eb-8ab6-1d7d71542c2e.png"  width="50%" height="50%"/>

* This dataset is data collected over a period of time for students at Dartmouth College.
* To obtain this dataset, the researchers distributed smart phones to students and conducted an Ecological Instantaneous Assessment (EMA) at the same time as collecting sensor data.
* In this project, students' responses to various Ecological Momentary Assessment (EMA) responses are used to predict students' depression.
* More information about the datasets associated with EMA can be found [Student life Dataset](https://studentlife.cs.dartmouth.edu/dataset.html).

## Step 1. Data Preprocessing
<img src="https://user-images.githubusercontent.com/62230550/165679392-0161d263-3c51-4057-9a87-90d085329276.png"  width="50%" height="50%"/>
Extract 'Sleep', 'Social', and 'Activity' data from the survey response json file and parse the actual values into index values.

## Step 2. Feature Extraction
<img src="https://user-images.githubusercontent.com/62230550/165681127-ee398d0c-6e7c-4c29-bd62-b71e5609ea0c.png"  width="50%" height="50%"/>
Extract statistical features from the previously parsed EMA response data.   

* Data is divided among trian/test users based on the previously added user id (uid).  
* Then, statistical features are extracted from the user's data using the describe function provided by pandas.  

Fill in the missing values of the data with the average value using the imputer.  
<img src="https://user-images.githubusercontent.com/62230550/165681895-27653da8-54e7-4e69-8ce9-881034df2337.png"  width="70%" height="70%"/>

## Step 3. Model training and prediction
![image](https://user-images.githubusercontent.com/62230550/165683463-bb0416e0-6209-4391-84d3-8600c09c1fc7.png)

* Depression prediction using only the sleep feature  
* Depression prediction using only the activity features
* Depression prediction using only the social features
* Depression prediction using all features

## Conclusion
* It can be confirmed that depression classification with better performance is possible by fusion of features extracted from various EMA data.
* Through this, the performance difference according to the actual feature representation can be confirmed.
