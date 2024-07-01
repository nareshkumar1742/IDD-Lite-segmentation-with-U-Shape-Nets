# IDD_Lite-segmentation-with-U-Shape-Nets
## Problem Statement:
	Given the road image dataset the task is to segment the image to seven classes where each class represent to roads, pathways, buildings, pedestrians etc. With the regular U-nets remarkable achievements can be made in segmenting images. The task of segmenting road based images require much more precision than other segmenting tasks. There needs to much precaution on the edges of the objects and roads so as to avoid accidents when any self driving cars use such models. The City scape dataset provides much of structured dataset wherein the roads images are from European countries. The Indian roads dataset is much complicated as we cannot expect much structured as in Europe.
	To solve this issue we have come up with the idea of leveraging the Edge Features. The model will perform Multi-training wherein it learns to detect both the edges and based on the edges it segments the output. By this we can achieve the edge level accuracy in classifying the pixels to heir corresponding labels
## Dataset :
	Dataset used for this study is IDD-Lite. For reference check the below link.
Ref link : https://idd.insaan.iiit.ac.in/dataset/details/
## Metrics:
	Mean Intersection Over Union
## Dataset Preprocessing: 
	The edge dataset are formed using the labels provided in IDD Lite dataset. Using  Sobel technique the gradients are obtained and the magnitude is calculated. This magnitude have value greater than 0 when there is a change from one label to another in a pixel. By this we can form the edge dataset wherein replacing any value greater that 0 will be changed to 1 and thus forming edge dataset corresponding for the labels.
## Architecture of the Model :
The architecture of the model for each of the encoder are attached in image format for references
	The loss function that is used for this model involves dice_loss + categorical_crossentropy_loss for the final output and dice_loss + binary_crossentropy_loss for edge based output.
