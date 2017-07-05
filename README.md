# Human-Detection From a Image

# Deep Learning

# Overview
Introduces an approach for Human detection in an image with sliding window. 
The Idea behind this approach is to train a CNN model on images which we want to detect.
After that make a sliding window on the image and query the trained model to produce appropriate output. 

# How to Run this Project
# Dependencies
This project requires Anaconda  Python 3.5  and the following Python libraries installed:
* tensorflow
* tflearn
* h5py
* hdf5
* SciPy
# Note: For Windows
Run this if you did not create environment using anaconda gui.
```
conda create -n my_env python=3.5  
conda install -c conda-forge tensorflow
 pip install tflearn
 ```
 # Dataset
  We capture the different videos in University of central of punjab by using camera and crop the images from video by matlab code  <b>Image_crop_video.m</b> .
  ## Traing Data
  Create a Data set frome a video. Capture a video from any Enviroment where humans or non hymans.
 you can get picture frome video by crop the single human or non human only pic
 you can crop picture by matlab code 
 * Image_crop_video.m
 Save picture in Data folder which have two other folder give name like 0 or 1
 * 0 contain humans pictures
 * 1 contains nonhumans pictures
 
 in our Train data set 1200 picture are use to train, 0 folder for human which contain 700 pictures and 500 NonHuman pictures in it.
 
 Some positive and negative images are as follows:
 
 ### Positive Image
![positive](https://user-images.githubusercontent.com/27928395/27203084-9c48dacc-523d-11e7-8d28-ec83d0636429.jpg)

 ### Negative Image
 ![ Negative](https://user-images.githubusercontent.com/27928395/27203047-75651376-523d-11e7-85f8-f892c8b38c4f.jpg)

## Test Data
 It like just train  data set make video and get pictures frome it like 10 to 15 nonhuman or human 
   and test the data from it
 
# How to Run the Model

Follwing  files are there to run the model
1. Train.py: Used to train the data.
2. Test.py :Load the image for testing which tell the traing accuracy. 
3. slide.py: which test to dectect the human
4.Image_crop_video.m: matlab code for cropping imaes from video.


  First run the matlab code on the captured video to detect images and create a dataset.After this run these files
  
  python Train.py  
  python Test.py  
  python slide.py 
  

 ## Model 

We use CNN in our case as CNN is best fit where we have dataset of images.

 # Layers
  1. Conv: 64 filters of size 3x3 with ReLU activation
  2. Pooling: with filter size 2x2
  3. Conv: 32 filters of size 3x3 with ReLU activation
  4. Pooling: with filter size 2x2
  5. Conv: 32 filters of size 3x3 with ReLU activation
  6. Pooling: with filter size 2x2
  7. Fully Connected: with 256 neurons and ReLU activation and dropout with probability 0.5
  8. Fully Connected: with 256 neurons and ReLU activation and dropout with probability 0.5
  9. Fully Connected output layer: with 2 neurons (equal to number of classes) and softmax classifier.
 ### Implementation
# Data preprocessing :
 Normalization
 # Data augmentation
 Redom rotation
 Redom blur
 # Sliding Window
 It is use for dectecting human on picture, it work after traing.
 
 
 # Result
 
 ## Training
    
We ran the cnn model for 10 epox and got accuracy 0.94 with validation accuracy of 0.96 using learning date of 
0.001 with adam optimizer.
 ![train](https://user-images.githubusercontent.com/27928395/27202983-30fc0b18-523d-11e7-9ede-be669e3e1595.png)
 
 # Testing
 ![test](https://user-images.githubusercontent.com/27928395/27203021-58888850-523d-11e7-9bb6-ec1cec32f165.png)
 # Sliding window 
   ![sliding window](https://user-images.githubusercontent.com/27928395/27748358-99d85036-5de8-11e7-88c2-8a26a9f4257f.jpeg)

 ### Discussion 
 I thoroughly studied the approach for human detection butt the best one is Convolutional Neural Networks in Deep learning 
 Because it took time to figure out the result but the results of this algorithm is accurate 99%
 
