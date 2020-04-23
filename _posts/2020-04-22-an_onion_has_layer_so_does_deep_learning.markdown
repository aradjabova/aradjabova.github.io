---
layout: post
title:      "An Onion Has Layer (so does Deep Learning)"
date:       2020-04-23 03:15:01 +0000
permalink:  an_onion_has_layer_so_does_deep_learning
---


Deep learning is basically machine learning that teaches computers to do things that humans do (in regards to comprehension). A good example of this is seeing a picture of a dog and knowing that its a dog. Simple, right? Well for computers they don't see a 'dog', it sees a bunch of numbers in a pattern. Just like we teach toddlers to identify each animal by showing multiple examples of the animal,  with computers you show (train) it the different numbers in the pattern of each animal. This is a known image classification.

Image classification using convolutional neural networks (CNN) are usually used to train computers. CNN's are able to read an image in by scanning the image in parts (2x2, 3x3, etc). Also when doing image classification, data augmentation is usually used to have models train on images with different variations, such as images with rotation, sheerness, diff colors, flip, etc. 

Image classification starts with a training set that the computer will learn to identify and classify what the image is about. The more data and variation of that data the better the model will be able to identify future images. In order to provide a variety of data, we use the data augmentation. The way that computers recognize images is by training on the specific images, pixels, and variations. Computers learn through layers, which is the process of computer scanning images in chunks. 



<img src="https://miro.medium.com/max/5266/1*QnKckNSZilG3HxytJZUoAw.png "  width="1000" height="300" />


 * Conv2D 
    * Scans the image and takes each pixel value in a 3x3 (or 4x4, depends on setting) part and multiplies it by a certain weight, adds the numbers and uses that number as the value of the output image of that pixel
    * Depending on the weights, the output image can be blurred, brighter, darker, etc. (basically slight photoshop)


 * MaxPooling2
    * Resizes the output image.
    * Takes 2x2 area of an image and chooses the max value in each area
    * Shrinks the image by a factor of two
    * After shrinking usually the images are used for additional filters (Conv2D) in order to train on smaller scales to find more patterns
  
	
 * Flatten
    * Because we will be using Dense next, we need to use Flatten to reduce the number of dimensions to one dimension
  
	
 * Dense
    * Dense layers are hidden layers that use different activation functions to find the weights of each parameter of the image in order to appropriately learn the images


  * Dropout
    * Usually set to 40%, which means that 40% of the parameters that go into the Dropout are set to zero
    * This helps the model not overfit

These are some helpful layers to use when creating a convolutional neural network for image classification. When these layers are used, the training will take longer, but the model will be able to learn as much as it can from the data.
