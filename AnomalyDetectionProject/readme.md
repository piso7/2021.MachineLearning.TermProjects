# Anomaly Detection Project => [Full Code](https://github.com/piso7/2021.MachineLearning.TermProjects/blob/main/SpamTextClassificationProject/kkw-ml-termproject-2.ipynb)
The project was conducted on the KAGGLE platform.  

Anomaly detection refers to finding objects or materials in data that exhibit a different pattern than expected.  
This project deals with the problem of detecting anomalies in industrial sites among various fields.

This project uses [MVTecAD(1) Dataset](https://www.mvtec.com/company/research/datasets/mvtec-ad)
* It is an abnormal situation detection data set in the manufacturing field among the industrial fields.
* The dataset provides images with a total of 15 classes.
* The product in the video was shot in the center of the video with the lighting and background designed to make it clear.

<img src="https://user-images.githubusercontent.com/62230550/165718327-f1e99fd4-1714-430f-ab1e-fba80052d67e.png"  width="50%" height="50%"/>
<img src="https://user-images.githubusercontent.com/62230550/165718493-01fee9c2-688c-44bd-b623-47a84fe3c40c.png"  width="50%" height="50%"/>

## Step 1. Reconstruction based anomaly detection
* Using PCA, the main components of train data composed of normal images are extracted, and the dimension of train data is reduced to n_component size by feature f (feature extraction)
* Extract feature f_test with PCA applied in before step on test data containing normal/abnormal images
* Restore feature f_test
* Extract the score by obtaining the difference between the original image and the restored image

## Step 2. Embedding feature based anomaly detection
* Extraction of normal image feature f using randomized PCA.
* Use one-class SVM to learn the support vector of f.
* Extracts the randomized PCA abnormal/normal image feature f_ts used in before step.
* One-class SVM classifies normal/abnormal with f_ts included in the normal distribution boundary.

## Step 3. Model training and prediction
![image](https://user-images.githubusercontent.com/62230550/166520019-071b48c2-991d-4e4e-9f26-5021e86379f3.png)
