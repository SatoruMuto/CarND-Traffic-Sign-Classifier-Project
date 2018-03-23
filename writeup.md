**traffic sign classifier**

The goals / steps of this project are the following:
* modify preprocessing of image, and network to achieve 93% or more accuracy. 
* evaluate new image with trained network, and show top5 probable IDs.


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### 1. Dataset Exploration

Dataset is provided in Udacity project kit, which include 
labeled 34799 of training data, 
labeled 4410 test data.
the number of classes are 43. 

All picture data size is already adjusted to 32x32 size. Those are colored data.



### 2. Design and Test a Model Architecture

1. Preprocessing

Before put data into network, all images will be coverted to grayscale, and brightness will be adjusted.
openCV is used to do this.

2. Model Architecture

Network is pretty much same as LeNet, except 2 added dropout in last 2 layer.
Therefore network structure is 
32 x 32 input
5x5x1x6 convolution layer
Relu activation
2 x 2 Max pooling
5x5x6x16 convolution layer
Relu activation
2 x 2 Max pooling
flatten 5x5x16 to 400
Fully connected layer, input 400 to 120
Relu activation
Random dropout (ratio = 0.5)
Fully connected layer, input 120 to 84
Relu activation
Random dropout (ratio = 0.5)
Fully connected layer, input 84 to 42

3. Model Training
Hyper parameter is adjucted to following,
Learning rate: 0.002
EPOCHS = 20
BATCH SIZE = 256

validation accuracy against validation data set is checked, and seems almost stable at 20 epochs.

4. Solution approach

Drop out affected to validation accuracy significantly. 
Then final adjustment was done with fine tune of hyper parameters, and brightness adjustement.

### 3. Test a model on New Images

1. Acuiring New images

I have used images from wikipedia, that are not a "picture" but drawing to show definition. 
(Also checked with some picture but seems that this drawing sometime are difficult to classify)

2. Performance on new images

The performance sometime vary. On submitted notebook, the rate is 0.6.
It will be 0.8 sometime, or be 0.4 sometime. 

3. Model certainty

Probability to label is on the graph in notetbook. 
Then it shows that the network gave 100% of probability to wrong answer in one case.
Seems that the newtwork has confidence to answer and there are no correlation between certenty and answer rate on my network.

The big factors that may affected to this result is 
-- size of sign are different between training data and test data from web. 
-- picture resolution. high definition picture may give better answer.Some training data are very hard to identyfy by human too. 
-- color data could work better?
-- 

