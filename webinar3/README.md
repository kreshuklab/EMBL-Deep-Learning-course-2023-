# Exercises for Webinar 3

We provide exercises in both pytorch and keras. Please try to work on both exercises to get an understanding of both libraries.

## Pytorch

In the first two exercises we follow up on the exercises from webinar 2 and implement a CNN and data augmentation for image classification on the cifar dataset.
The last exercise provides an introduction to image segmentation with a U-net to prepare us for the course and introduce a very important method for bioimage analysis.

For the pytorch exercises, please use the `DL Course(Pytorch)` environment in BAND. You can start it via `Applications->Programming->DL Course(Pytorch)`.

## Keras

In the subfolder `keras` you will find 3 different notebooks that demonstrate a DL based segmentation workflows of increasing complexity. Please also note the questions/exercises (<span style="background-color:lightblue">marked by blue back ground</span>).   

#### `1_semantic_segmentation_2D.ipynb` 

A simple *semantic* segmentation pipeline for 2D images using a good old UNet network. Always a good starting point and a solid baseline to compare against when using more fancy tools! 


#### `2_instance_segmentation_2D.ipynb.ipynb`

A *instance* segmentation pipeline for 2D images using a *stardist*  network, a specific detection/segmentation method for roundish objects. The data consists of fluorescently labeled nuclei, which are typically quite roundish thus rendering this approach suitable. 


### `3_instance_segmentation_3D.ipynb.ipynb`

A *instance* segmentation pipeline for 3D images using a *stardist* 3D network. The data consists of synthetically created nuclei.


## Additional materials:

 * [Python Classes Basic Tutorial](https://www.w3schools.com/python/python_classes.asp)
 * [Python Classes Basic Tutorial 2](https://www.learnpython.org/en/Classes_and_Objects)
 * [Python Classes In-depth Tutorial](https://hackernoon.com/improve-your-python-python-classes-and-object-oriented-programming-d09ff461168d)
 * [Intuition Behind UNet](https://towardsdatascience.com/u-net-b229b32b4a71)
