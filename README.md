# Transfer-Learning U-Net
A project on using Transfer Learning to segment lung pneumonia. 

## 1.0 Motivation
Segmentation is costly to annotate. Requires someone with a degree of training to go through each slice and carefully contour what you're looking for. Given the recent event of COVID, pneumonia is only present as a serious complication of the case. This project is motivated to help patients by using machine learning to detect pneumonia. 

## 2.0 Data Exploration 
The image shows a chest X-ray where the pneumonia is encapsulated. Each image shape is [1, 512, 512, 1]. The first column is the z-axis, the second is the y-axis, the third is the x-axis, and the fourth is the channel. 

Checking the label distribution. About half of the cases have pneumonia, and the other half do not

Exploring the pneumonia pixel size distribution, it is right skewed, where most labels are around 20k pixels. The image total pixel is 512 x 512 = 262144. Most pneumonia cases cover about 7.6% of the overall image size. 

Lastly, check the chest image distribution with pneumonia and without pneumonia. 


There is a slight change in the distribution of cases with pneumonia against no pneumonia.


## 3.0 Transfer Learning and Preprocessing
The ResNet-50 backbone used for transfer learning in this experiment requires the following modifications:
- data input must be 2D (H X W) in shape
- data input must be 3 channels in depth
- data input must be scaled between [0, 1]

I preprocessed the data by subsampling by 8 to prevent potential overfitting.



