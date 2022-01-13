# Unsupervised Machine Learning Methods for outlier detection 
In this repository you can find the implementation of the Semester Project: "Unsupervised Machine Learning Methods for outlier detection"

## Table of content
- [the description of the project task](#Introduction)
- [datasets overview](#datasets)
- [description of methods](#methods)
- [the code structure](#code_structure)
- [how to run the code](#run)
- [perspectives](#outlook)

## <a name="Introduction"></a>  Introduction
This project focuses on implementation of unsupervised Machine Learning methods for outlier detection to avoid mistakes when manually labeling data 
using deeplabcut GUI before the training process.

<p align="center">
</br> <img src="./imgs/labels1.png " width="600"></br>
</p>


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

## <a name="methods"></a> Methods description

### Unsupervised ML methods: k-means and DBSCAN
The main idea is to obtain the geometric features of labels on images, cluster labels using unsupervised Machine Learning methods, and identify images with bad labels.

You can see the general pipeline below:
1. Data visualization.
2. Computing features: 
      - the distance between every two body parts;
      - angle and angle sign between three points
	  (e. g. left ear, snout, right ear).
3. PCA.
4. Clustering.

You can see the results of k-means and dbscan clustering method applied to mice dataset with 40% of corrupted images below:
<p align="center">
</br> <img src="./imgs/clustering.png " width="600"></br>
</p>

</br>

The same clustering methods doesn't allow to indicate all corruted images for horse data. The main challenge of horse data is that images are very different:
- more body parts
- different quality of images
- sometimes only part of the horse is visible

<p align="center">
</br> <img src="./imgs/horses.png " width="800"></br>
</p>


###  Impact of the swap ears error

To understand how the swap ears error affect the performance of the DLC algorithm we conducted the following experiment.
Here we consider the [mice dataset](https://raw.githubusercontent.com/DeepLabCut/DeepLabCut/master/examples/openfield-Pranav-2018-10-30/labeled-data/m4s1/CollectedData_Pranav.csv).

Firstly, we add swap ears error on image in the mice dataset in 6 different proportions: 0 (without corrupted images), 0.2 (20% of images have ears swap error), 0.4, 0.6, 0.8 and 1 (all images have ears swap error).

Then we train the network with the DLC algorithm and run 6 different experiments to see how many images with errors are identified.

In the graph below, you can see the error of the DLC algorithm in pixels on train and test samples depending on the number of corrupted images.

<p align="center">
</br> <img src="./imgs/impact1.png " width="800"></br>
</p>

In the graph below, you can see the [mean Average Precision](https://cocodataset.org/#keypoints-eval) of the DLC algorithm on train and test samples depending on the number of corrupted images.

<p align="center">
</br> <img src="./imgs/impact2.png " width="800"></br>
</p>

The main limitation of the method is that the test sample contains only 6 images. 

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
- Find impact of other errors on the performance of the DLC algorithm
- Explore already existing methods with visual transformers and apply them to our data set

