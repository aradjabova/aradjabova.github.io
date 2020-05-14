---
layout: post
title:      "Identifying Blurry Images"
date:       2020-05-14 13:08:38 -0400
permalink:  identifying_blurry_images
---


Autoencoder is an awesome tool that is used to visually see what exactly the model is learning when we use image classification. Autoencoders can take a clear focused image and condense the information in it so that the smaller "image" is the most valuable and most important part of the image. Using the smaller, condensed version of the image the model then can recreate, expand the image into the same shape of the original images. The recreated images are very similar to the original images, though they are blurrier versions. They lack the parts of the image that makes it very focused and loses some of the backgrounds. 



<img  style="float: left;"  src="https://drive.google.com/uc?id=1XjcRJuNTI7B7AsZrNIg4bRJ7_yuqr4lV"   height="400" width="300">

<img   src="https://drive.google.com/uc?id=1L-FxmT7JPv7IhhABZ3ceiI_f_5o8HK8f"  height="400" width="300">




As shown above, the left image is a more focused image of the forest image and the autoencoder created the image on the right that is blurrier than the original one. This shows that the autoencoder was able to dictate that the most important and valuable information is the parts that look similar to the original image. The parts that were blurred were not apart of the condensed information meaning that it did not need those parts to be able to recreate a very similar image.

When creating an image classifier we usually use the original image for the classifier to learn from in a big deep neural network and be able to make predictions from.  Since autoencoder can find the most valuable parts of an image (to be able to recreate it), I had created an experiment where the input images for the image classifier would be these augmented images that were created by an autoencoder. The hypothesis was that these augmented images that the autoencoder created will have a better chance at accurately classifying the images because the most important parts of the image were available to train on. 

Unfortunately, the experiment resulted in the augmented image classification to be worse than the image classification of the original image. According to the accuracy and loss validation of the model, shown below, it is clear that the model can learn well on the training data (the augmented image), but when tried to verify with an image that the model has never seen before the model was unable to accurately classify the images. The training data for both the graph is steadily increasing which is an indication of the model learning. The validation portion of the data shows that the model is overfitting to the training data and is unable to truly learn from the images by not being able to understand the test images that the model had never seen. 


<img  style="float: left;"  src="https://drive.google.com/uc?id=1OdcLhcQWxD-Zy3oB3rkMPfMIOHcFH0Xu" height="400" width="400"!>
<img   src="https://drive.google.com/uc?id=1yJWFmObhYEHB6vYhErv0jylouqiQy4Dj"  height="400" width="400"!>



Lastly, the confusion matrix below shows how the model of the classified test data. As shown below the classifier was unable to classify many of the images correctly and does not seem like a viable classifier. Due to the model overfitting to our training data, the model would need to be redone to be able to extract more information from the images and be able to learn the most important parts of each image category in order to identify it.


<img  style="float: center;"  src="https://drive.google.com/uc?id=1OZzWsICFEukRUo5evZSQg4aiZnKaHZXo"  height="400" width="400"!>
