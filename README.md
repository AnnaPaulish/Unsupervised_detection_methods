# Unsupervised Machine Learning Methods for outlier detection 
In this repository you can find the implementation of the Semester Project: "Unsupervised Machine Learning Methods for outlier detection"

## Table of content
- [the description of the project task](#Introduction)
- [datasets overview](#datasets)
- [the code structure](#code_structure)
- [how to run the code](#run)
- [perspectives](#outlook)

## <a name="Introduction"></a>  Introduction
This project focuses on implementation of unsupervised Machine Learning methods for outlier detection to avoid mistakes when manually labeling data 
using deeplabcut GUI before the training process.

<p align="center">
</br> <img src="./imgs/labels1.png " width="600"></br>
</p>
The main idea is to obtain the geometric features of labels on images, cluster labels using unsupervised Machine Learning methods, and identify images with bad labels.

You can see the general pipeline below:
1. Data visualization.
2. Computing features: 
      - the distance between every two body parts;
      - angle and angle sign between three points
	  (e. g. left ear, snout, right ear).
3. PCA.
4. Clustering.

## <a name="datasets"></a>  Dataset overview

For this project we used the following datasets:
- [Mice dataset](https://zenodo.org/record/4008504#.Yds2QmjMI2z): 1178 images 
	
<p align="center">
</br> <img src="./imgs/micedataset.png " width="500"></br>
</p>



- [Horse dataset](http://www.mackenziemathislab.org/horse10): 3069 images
<p align="center">
</br> <img src="./imgs/horsedataset.png " width="500"></br>
</p>


## <a name="code_structure"></a>  The code structure
In the folder `horse_dataset` contains horse-10 data set.

In the folder `scripts` you can find two files:
- `clustering_and_LRtest_mice.ipynb` - consisting the code for mice data set
- `clustering_and_LRtest_horse.ipynb` - consisting the code for horse-10 data set

## <a name="run"></a> Running the code 

Clone the repository to your preferred location using the following command:
```
git clone https://github.com/AnnaPaulish/Unsupervised_detection_methods.git
```
Then open the code using [Jupyter notebook](https://jupyter.org/).

## <a name="outlook"></a> Conclution and Perspectives
We can see that the geometric features for horse data not sufficient for solving the problem.

The horse data is much more complex than mice data because they have more body parts and different types of images, sometimes only part of the horse is visible.

If we want to solve to detect bad labels in real-life images we need to consider other features or methods.

Future steps:
- Find impact of the swapping or other errors to the performance of DLC algorithm
- Explore already existing methods with visual transformers and apply them to our data set

