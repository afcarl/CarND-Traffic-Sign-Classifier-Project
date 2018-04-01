## Lab Notebook writeup

### 1 Data set
* Number of training examples = 34799
* Number of testing examples = 12630
* Image data shape = (32, 32, 3)
* Number of classes = 43

![Data Distribution](https://imgur.com/NFHWyZm.png)

#### Preprocessing

The two most obvious preoprocessing steps taken were normalize & greyscale. Both of these reduce the dimensionality of the data. Greyscaling removes
unecessary noise such as color changes but luminance instead. Normalizing also takes down the range of data the algo needs to cover.

### 2 Network Architecture

Used LeNet.

|Layer|Description|
|----|:-----:|
|Input|32x32x3|
|Conv Layer|28x28x6|
|Activation|Relu|
|First Output/2nd Input | 10x10x6 |
| 2nd Layer| Relu, Conv|
|3rd Layer Input |Fully Connected, 400x120|
|4th Layer | Fully Connected, 120x84|
|5th Layer | Fully Connected, 84, 43|

### 3 Hyperparameters for Training
---

I was frustrated by the struggle to get the .94 but i finally managed to make
it work.

| Batch | Epoch | Final Validation Accuracy |
|-------|:-----:|---------------------------|
| 128   | 20    |         .90 |
| 64 | 20 | .94 |
| 32 | 20 | .93 |


### 4 Model Construction

This was rough! I started and ended with a LeNet. How to construct a new NN
architecture is beyond me for now. This was the first architecture chosen. I've heard of LeNet off and on over the years so I immediately went with that. This way I could focus on hyperparameters.

I found that a batch size of 64 and 20 epochs was most effective.

### Test on a new model image

I picked 'no cars', Right-of-way at the next intersection, 'Priroity road',
'no vehicles', and 'general caution'.

My model didn't get any of them right. :( I believe this could be because of
how the images i found was preprocessed. I'm out of time and can't figure this
out.

#### Challenges for new example images

#Are there any differences in the signs, their position or image quality that might influence the results?

The only thing I can see that has an additional characteristic is the quality
and make of camera that was used to take the picture. I noticed that some of the
 color hues and values are different compared to the ones taken more recently.
 The position and distance from the camera, for example if the pictures were
 taken at 90 degrees from the surface of the sign.

####
