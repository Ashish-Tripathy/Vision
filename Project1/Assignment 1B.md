# Assignement 1B

## What are Channels and Kernels (according to EVA)?

### Channels:
A set of distinguishable features together form an image. Multiple features can represent similar aspect of the image. Consider the example of Chicken Biryani. To prepare Chicken Biryani we need lots of different ingredients like Turmeric, Red chilly powder, salt, Chicken pieces, tomato, onion, green chillies, garllic etc. All these ingredients can be grouped under logical groups like Vegetables, Chicken pieces, Masala powders. So these groups having similar ingredients can be thought of as channels with resect to image. So basically a Channel is a bag or container of similar features.

### Kernels:
Kernels are filters or a matrix which help in extracting features from an image. A kernel matrix is slid over the image pixels, doing convolution operation on each slide to produce features. A convolution operation involves multiplication of each matrix element with the image pixel and then summing up the result to generate a single number. A matrix produced from this operation is the convolved feature.


## Why should we only (well mostly) use 3x3 Kernels?

1. A 3x3 kernel is a odd kernel which helps to maintain symmetry to extract features from the a neighbourhood of correlated pixels of an image. Any odd kernel will have an origin point and can capture information about its neighbourhood unlike an even kernel where origin will be ambiguous
2. 3x3 kernel is a building block for all the possible odd kernels. We can produce all sorts of odd kernels by stacking multiple 3x3 kernels. Like a 5x5 kernel can be produced by using 2 3x3 kernels
3. Stacking 3x3 kernels to have larger odd kernels results in less parameters when compared to directly using a larger odd kernel. Lesser parameters means faster computation
4. Many popular GPUs are optimised to efficiently use 3x3 kernels. Using any other kernel reduces the performance a lot


## How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199 (show calculations)

We need to perform <b><i>100</i></b> 3x3 convolution operations.
### Calculations:
199x199->197x197->195x195->193x193->191x191->189x189->187x187->185x185->183x183->181x181->179x179->177x177->175x175->173x173->
171x171->169x169->167x167->165x165->163x163->161x161->159x159->157x157->155x155->153x153->151x151->149x149->147x147->145x145->
143x143->141x141->139x139->137x137->135x135->133x133->131x131->129x129->127x127->125x125->123x123->121x121->119x119->117x117-> 
115x115->113x113->111x111->109x109->107x107->105x105->103x103->101x101->99x99->97x97->95x95->93x93->91x91->89x89->87x87->85x85->83x83-> 81x81->79x79->77x77->75x75->73x73->71x71->69x69->67x67->65x65->63x63->61x61->59x59->57x57->55x55->53x53->51x51->49x49->47x47->45x45->
43x43->41x41->39x39->37x37->35x35->33x33->31x31->29x29->27x27->25x25->23x23->21x21->19x19->17x17->15x15->13x13->11x11->9x9->7x7->
5x5->3x3-> 1x1
