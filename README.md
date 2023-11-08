# Facial-Keypoints-Detection
Solution for Kaggle´s Facial Keypoints Detection challenge

# Problem Description
The objective is to predict the location of facial keypoints on portraits. This is based on a [Kaggle challenge](https://www.kaggle.com/competitions/facial-keypoints-detection/overview).

# Dataset
The dataset consists of 7049 black and white images. The images are 96x96 pixels. There are 15 facial keypoints which are identified, allthough not all images have all facial keypoints identified. Each facial keypoint is given by real (x,y)-coordinates.

# Data Augmentation
We use horizontal reflections for data augmentation, as well as perturbations by a random affine function. 
The random affine function has normally distributed coefficients centered at the identity. Each perturbation can be seen as a combination of rotation, traslation, zooming and sheering.
A grid search was used to optimize the number of perturbation images added as well as the variance of the perturbations. 

# Model
We use a convolutional neural network to solve the problem. It consists of 3 convolutional layers with ReLu activation functions and 2x2 maxpooling, followed by 2 locally connected layers, an average global pooling and a dense layer. The model has 1.5 million parameters.

# Results
The private score of the model is 1.519 and the public score is 1.883 on Kaggle. This would be 6/176 placement at the time of closure of the Kaggle challenge.
