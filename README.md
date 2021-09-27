# Understanding SSL by implementing PiCIE.
PiCIE Unsupervised Semantic Segmentation using Invariance and Equivariance in Clustering: 
[[paper](https://openaccess.thecvf.com/content/CVPR2021/papers/Cho_PiCIE_Unsupervised_Semantic_Segmentation_Using_Invariance_and_Equivariance_in_Clustering_CVPR_2021_paper.pdf)]

<p align="center"> <img src='assets/teaser2.png' align="center" height="320px"> </p>
<p align="center"> <img src='assets/teaser.png' align="center" height="250px"> </p>

## Setup
Setting up for this project involves installing dependencies and preparing the datasets. 

### Installing dependencies
First, you should install all the dependencies, run the following line in the linux console:

~~~
conda env create -f env.yml
~~~

### Preparing Dataset 

Create a softlink to the parcial COCO dataset, this directory must be at the same level of the .py codes. Run this lines in the linux console.

~~~
ln -s "/media/user_home1/eslozano/AML/SSL-hw/ssl_segmentation/COCO_Segment/" "Your_directory"
~~~


## Running PiCIE 
First, create a directory named Results, then run this code to run train_picie.py

~~~
CUDA_VISIBLE_DEVICES=x taskset -c x-x python train_picie.py --data_root "COCO_Segment" --save_root "Results"
~~~

## Homework

## Point 1 [0.7 Points]

Review the code and try to understand the connection between the code and the paper. Then run the train file and save the results.

In the report, identify and explain where in the code is the generation of the pseudo-tags. 

Also discuss:
- Why they have used a Siamese architecture?
- Why the generated clusters have semantic meaning? (Hint: Check Section 3 of PIECE [[paper](https://openaccess.thecvf.com/content/CVPR2021/papers/Cho_PiCIE_Unsupervised_Semantic_Segmentation_Using_Invariance_and_Equivariance_in_Clustering_CVPR_2021_paper.pdf)])


## Point 2 [1.5 Points]

Modify the code in a way that only 2 transformations (1 of color, 1 of geometrics) can be aplied to images. Then run the train file and save your results.
Run other experiments and check which of the transformations (color or geometric)have more influence on good results.

In your report, describe the changes that you did and compare them with the baseline. It has a better performance? Which transformations are already implemented? What is the implication of using 2 or more transformations? Try to relay the paper to the response.

## Point 3 [1.5 Points]

Train a supervised segmentation network of your choice and discuss the differences between the architectures. Note: You can perform this process with another partner.

In the report, discuss what impact the architectures have on the results obtained.

## Point 4 [1.3 Points]

Visualize the 3 experiments [reference model - supervised model - model of your choice] and analyze them qualitatively and quantitatively
Hint: Check this link [jupiter notebook](visualize.ipynb) that the authors did to visualize results.



