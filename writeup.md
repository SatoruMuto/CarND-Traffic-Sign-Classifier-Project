**traffic sign classifier**

The goals / steps of this project are the following:
* modify preprocessing of image, and network to achieve 93% or more accuracy. 
* evaluate new image with trained network, and show top5 probable IDs.


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps.   
  1. Convert original image to grayed image.
  2. Apply gaussian_blur to remove noise
  3. Apply canny to extract edge
  4. take data from necessary regione
  5. calculate left line and right line from No4 line data.

In order to draw a single line on the left and right lanes, I created the draw_onelines() function.
This function calculate average slope of right lines and leftlines, starting point and end point of each line.
starting point is defined as the bottom of picture.


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when line are multiple, or line length is not enough.

Another shortcoming could be below
    1. when vehicle change lane, this program could not identify line.
    2. Different line color can not be detected
    3. If other vehicle (especially white vehicle) is very close, line will be lost.
    4.    


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to add robustness to multiple edge detection. The average method may not be the best method to make 1 line. 


## 

### 4. requirement compliance 

 - 4-1 Does the pipeline for line identification take road images from a video as input and return an annotated video stream as output?
   Done  
 - 4-2  Has a pipeline been implemented that uses the helper functions and / or other code to roughly identify the left and right lane lines with either line segments or solid lines?   
   Roughly. Accuracy need to be improved...
 - 4-3 Have detected line segments been filtered / averaged / extrapolated to map out the full extent of the left and right lane boundaries? 
    Roughly done. Accuracy need to be improved...
 - 4-4 Has a thoughtful reflection on the project been provided in the notebook?  
    Yes

## reference used to complete this project

ref1 : https://qiita.com/k_sui_14/items/92fd84f35245ad0be464  
ref2 : http://postd.cc/image-processing-101/  
