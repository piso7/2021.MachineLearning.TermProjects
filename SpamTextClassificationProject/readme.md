# Spam Text Classification Project => [Full Code](https://github.com/piso7/2021.MachineLearning.TermProjects/blob/main/SpamTextClassificationProject/kkw-ml-termproject-2.ipynb)
The project was conducted on the KAGGLE platform.  

This project uses [SMS Spam Collection Dataset](https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset)
* A set of SMS-tagged messages collected for SMS Spam investigation.
* A total of 5574 English messages are provided, labeled Spam(1), Ham(0).

## Step 1. Text Data Preprocessing
* Remove non-text objects such as emojis or numbers and dots.
* Make words lowercase: The machine treats the same word with different case as different words.
* Stopword Removal: Stopwords are words that do not affect the importance of text in text classification. (ex: the, we, a , will)
* Stem: The Bag of Word model i will use in this project will be affected by more frequent occurrences of words. Several words with the same meaning (ex: runnable, running , is run) have been changed to the same.

## Step 2. Feature Extraction
### Bag of Word(BoW)
<img src="https://user-images.githubusercontent.com/62230550/165708737-ed40df29-824e-432f-ac68-b87187a2266f.png"  width="50%" height="50%"/>

* Get all the words in all texts, count the number of occurrences of each word, and select a specific word (Cluster Word) that occurs most frequently.  
* Assuming that a total of 1000 cluster words are selected, the number of occurrences of these 1000 words becomes a feature of the classification problem.
* Classification proceeds by learning the classifier with the extracted features.
* Use CountVectorizer provided by Sklearn.

## Step 3. Model training and prediction
* For this project, I used SVM, which is said to work best with BoW.  

![image](https://user-images.githubusercontent.com/62230550/165713812-acc48664-d1f2-4e96-bae4-e4961db070fc.png)
