# Human Behavior Classification Project => [Full Code](https://github.com/piso7/2021.MachineLearning.TermProjects/blob/main/HumanBehaviorClassificationProject/fork-of-17011805-5.ipynb)
The project was conducted on the KAGGLE platform.  

One of the ways to use video to classify behavior is to use a classifier to judge behavior by representing a video with a feature (=1D vector).
This project also aims to describe video features in many ways and judge them by their different classifiers.

This project uses mini_ucf101 dataset
* A dataset created by reducing the size of the UCF101 dataset.
* The dataset provides images with a total of 15 classes.
* There are 101 types of behaviors, which are the same as UCF101, but 25 videos (train+test: 20+5) are sampled for each behavior, and a total of 2525 videos (train+test: 2020+505).

<img src="https://user-images.githubusercontent.com/62230550/166525739-94bd6859-8572-4ca7-ae0f-5e7f85048efe.png"  width="50%" height="50%"/>


## Frame Feature Extraction
<img src="https://user-images.githubusercontent.com/62230550/166544553-c8914679-c58f-4e15-952f-98119bf54bd3.png"  width="50%" height="50%"/>

### 1. BoVW(Bag of Visual Word)
* It is a method of finding the characteristic part of the image (= feature point, visual word) and selecting the representative characteristic point (codebook) and describing the image feature with their distribution.
#### 1) Visual word Extraction

<img src="https://user-images.githubusercontent.com/62230550/166545749-25e9fd52-af5d-4632-8dda-08ae48475fef.png"  width="50%" height="50%"/>

* The visual word extraction algorithm SIFT, also called the Local descriptor, is designed to be tough on the size and rotation of objects in the image, and detects and describes where the visual word will be in the image.
* The visual word described consists of a 128-dimensional vector and is used as a feature point.

#### 2) Selecting the representative characteristic point (codebook)

<img src="https://user-images.githubusercontent.com/62230550/166552343-665feee5-31db-44ab-a0e5-5fc2e21f074f.png"  width="50%" height="50%"/>

* After extracting the visual word from all images, you must select the representative feature point (Codebook)
* To do this, the k-means algorithm is used to divide all 128-dimensional visual words into k clusters based on distance, and each cluster's center point is used as a representative feature point (codebook).
* Note that you should select a representative feature book using only the visual word obtained from the frame of the learning video.

#### 3) Calculate the distribution of representative feature points (codbook) by image

<img src="https://user-images.githubusercontent.com/62230550/166552412-cad506a3-168e-468b-a2a1-95f2852e00c3.png"  width="50%" height="50%"/>

* For each image, assign the extracted visual word to the nearest representative feature point (codebook) by comparing the distance with the calculated k representative feature points (codebook).
* The assignment process allows the generation of a histogram, and the BoVW algorithm uses it as a feature of the image.
* Note that you should obtain histogram features for each frame of the learning video and evaluation video.

### 2. VLAD (Vector of Locally Aggregated Descriptors)

<img src="https://user-images.githubusercontent.com/62230550/166552809-196f2fc4-251a-47a3-af74-69bf92feed5b.png"  width="40%" height="40%"/>

* If BoVW calculates the distribution of representative feature points for each image and uses histogram-type features, VLAD allocates the visual words in order of distance to the representative feature points, calculates the vector difference between the two, and adds the vector difference value of the same code word.
* For this reason, the method of extracting visual words used in BoVW and selecting a representative characteristic point (codbook) is used the same.
