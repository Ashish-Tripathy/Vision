# Architectural Basics



Learning Rate,




Number of Epochs and when to increase them,
DropOut
When do we introduce DropOut, or when do we know we have some overfitting



How do we know our network is not going well, comparatively, very early
Batch Size, and effects of batch size

LR schedule and concept behind it
Adam vs SGD


## Order in which I will make the architectural desicions:

1. Receptive Field - Once I get the data, I will explore the images at hand and the problem to be solved. Looking at the images will help us decide the receptive field that we should target for our model to be able to detect or classify images.
2. How many layers - Once we have an idea of the receptive field that might help us achieve our target, we can decide on how many convolution, bottleneck layers wil be required for us to achieve the required receptive field. Also based on this info and sixe  image we can decide where we need to stop convoluting and introduce prediction layer.
3. Softmax - Due to discussion over softmax in this session, I will decide upon softmax at this time based on the problem I am trying to solve. As discussed, if we are predicting very critical scenarios like Cancer detection, we should think twice before using Softmax and research on some other Activation function for our model
4. Image Normalisation - The input images will go through this data preparation step where the entire input image is batch normalised
5. 3x3 convolution - We will only be using this convolution
6. 1x1 convolution - whenever we have to decrease the number of channels, we will use 1x1 convolution
7. Kernels and how do we decide the number of kernels - based on the complexity of the train and validation images, we need to decide how much wide the architecture should be. The number of kernels also effect the number of parameters and thus the performance, so based on the resouce constraints we need to chose appropriate number of kernels
8. Concept of transition layer - decision on whether to have  a transition layer. This layer will have a 1x1 and a Maxpooling. We generally include the transition layer, but if the size of image is very small we might have to rethink using these layers
9. Position of Transition layers - How many convolutions after we need to have the transition layer, needs to be decide now
10. Maxpooling - reduces the resolution of the image by passing the maximum pixel under the layer. It also doubles the RF, so need to be strategically placed
11. Position of MaxPooling - Maxpooling in the transition layer, it can be before or after the 1x1 in the transition layer
12. The distance of MaxPooling from Prediction - Maxpooling layer should be some convolutions away from the Prediciton layer depending on the train and validation image sizes
13. When do we stop convolutions and go ahead with a larger kernel - We must stop where the final convolution output will have some useful representation. it should not be convolved until we get 2x2 or 1x1. Ideally for a 400x400 we can stop at around 11x11 - 7x7 maximum.
14. Batch Normalization - This technique will normalise the features being extracted in the convolution layers, this will increase the performance and accuracy of the network
15. The distance of Batch Normalization from Prediction - placement discussion for BN is not very important for me, I use it after every convolution.
16. When to add validation checks - when we fit the first iteration of the model, we can have the validation accuracy displayed along with train accuracy. This wil give us the intution of how our model is behaving for each epoch
17. How do we know our network is not going well, comparatively, very early -  we need to check the train and validation accuracy in the initial epochs for comparing multiple runs which are just changed in architecture and not on other hyperparameters like dropout, bacth size etc. 
18. Number of Epochs and when to increase them - Based on the increase in training and validation accuracy we can get an idea of how many epochs to run. Like if the model is not completely trained, we can run it for more epochs.
19. Dropout - Dropout drops some neurons randomly, introducing regularisation in the training process
20. When do we introduce DropOut, or when do we know we have some overfitting - whenever we see the gap between training accuracy and validation accuracy is increasing with higher training accuracy and lower validation accuracy
21. Learning Rate - the learning rate needs can be altered further once we see how the train accuracy and validation accuracy are changing in the training verbose
22. LR schedule and concept behind it - decide on the LR schedule like change LR by some decay factor after few epochs. This needs to be decided based on the performace observed i the training verbose
23. Batch Size, and effects of batch size - Appropriate Batch size needs to be decided based on the resource constraints. Higher batch size are faster but can create OOM issues. Lower batch size might effect the accuracy and also effect the representation of each class in the batch
24. Adam vs SGD - If still we donot get much success we can think changing the optimisation algo and repeat the above steps.

