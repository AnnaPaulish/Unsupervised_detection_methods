# Unsupervised Machine Learning Methods for outlier detection 
In this repository you can find the implementation of the Semester Project: "Unsupervised Machine Learning Methods for outlier detection"

## Table of content
- [the description of the project task](#Introduction)
- [datasets overview](#datasets)
- [the code structure](#code_structure)
- [how to run the code](#run)
- [perspectives](#outlook)

# <a name="Introduction"></a>  Introduction
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

# <a name="datasets"></a>  Dataset overview

For this project we used the following datasets:
- [Mice dataset](https://zenodo.org/record/4008504#.Yds2QmjMI2z): 1178 images 
	
<p align="center">
</br> <img src="./imgs/micedataset.png " width="500"></br>
</p>



- [Horse dataset](http://www.mackenziemathislab.org/horse10): 3069 images
<p align="center">
</br> <img src="./imgs/micedataset.png " width="500"></br>
</p>


# <a name="code_structure"></a>  The code structure

# <a name="run"></a> Running the code 

# <a name="outlook"></a> Conclution and Perspectives
