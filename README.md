# Image Spatial Filtering

Filtering is a technique for modifying or enhancing an image. Spatial domain operation or filtering (the processed value for the current pixel depends on both itself and surrounding pixels). Hence Filtering is a neighborhood operation, in which the value of any given pixel in the output image is determined by applying some algorithm to the values of the pixels in the neighborhood of the corresponding input pixel. A pixel's neighborhood is some set of pixels, defined by their locations relative to that pixel. 

## 1. Smoothing Spatial Filter
Smoothing filter is used for blurring and noise reduction in the image. Blurring is pre-processing steps for removal of small details and Noise Reduction is accomplished by blurring.

### *Average filter*
The average filter is a uniform low pass filter. It is used to remove fine details and noise from the images.

The problem with average filter is that it blurred the edges when large neighborhoods are used to remove noise. The Point Spread Function (PSF) of average filter is “Sinc” in special domain which has negative side lobes causes ringing effects as well. 

### *Gaussian filter*
The Gaussian filter is a non-uniform low pass filter. It is also used to remove fine details and noise from the images.

The PSF of gaussian filter has positive side lobes which avoid ringing effects. The gaussian filter depend upon the value of standard deviation as larger values of standard deviation produce a wider peak (greater blurring).
