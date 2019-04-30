# Assignement 1B

## What are Channels and Kernels (according to EVA)?

### Channels:
A set of distinguishable features together form an image. Multiple features can represent similar aspect of the image. Consider the example of Chicken Biryani. To prepare Chicken Biryani we need lots of different ingredients like Turmeric, Red chilly powder, salt, Chicken pieces, tomato, onion, green chillies, garllic etc. All these ingredients can be grouped under logical groups like Vegetables, Chicken pieces, Masala powders. So these groups having similar ingredients can be thought of as channels with resect to image. So basically a Channel is a bag or container of similar features.

### Kernels:
Kernels are filters or a matrix which help in extracting features from an image. A kernel matrix is slid over the image pixels, doing convolution operation on each slide to produce features. A convolution operation involves multiplication of each matrix element with the image pixel and then summing up the result to generate a single number. A matrix produced from this operation is the convolved feature.


## Why should we only (well mostly) use 3x3 Kernels?

We mainly 
