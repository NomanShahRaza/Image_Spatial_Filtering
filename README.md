# Image Spatial Filtering
<p align="justify">
    Filtering is a technique for modifying or enhancing an image. Spatial domain operation or filtering (the processed value for the current pixel depends on both itself and surrounding pixels). Hence Filtering is a neighborhood operation, in which the value of any given pixel in the output image is determined by applying some algorithm to the values of the pixels in the neighborhood of the corresponding input pixel. A pixel's neighborhood is some set of pixels, defined by their locations relative to that pixel.

 

## 1. Smoothing Spatial Filter
<p align="justify">
Smoothing filter is used for blurring and noise reduction in the image. Blurring is pre-processing steps for removal of small details and Noise Reduction is accomplished by blurring.

### *Average filter*

The **average filter** is a uniform low pass filter. It is used to remove fine details and noise from the images.

<p align="justify">
The problem with average filter is that it blurred the edges when large neighborhoods are used to remove noise. The Point Spread Function (PSF) of average filter is “Sinc” in special domain which has negative side lobes causes ringing effects as well. 
</p>

### *Gaussian filter*

The **Gaussian filter** is a non-uniform low pass filter. It is also used to remove fine details and noise from the images.

<p align="justify">
The PSF of gaussian filter has positive side lobes which avoid ringing effects. The gaussian filter depend upon the value of standard deviation as larger values of standard deviation produce a wider peak (greater blurring).
</p>

![1_1](https://user-images.githubusercontent.com/84965044/153725509-e6b05c2d-996e-4ff0-8c27-23b6f9c6d2d6.jpg)

![1_2](https://user-images.githubusercontent.com/84965044/153725507-9a10222f-ae2b-4436-9b8a-8a306ad84953.jpg)



## 2. Edge detection filter

Edge detection is an image processing technique for finding the boundaries of objects within images. It works by detecting discontinuities in brightness.

### *Prewitt and Sobel filters*
<p align="justify">
Prewitt and Sobel filters are directional edge detector that are used to detect edges in either horizontal or vertical direction. A kernel of 11 by 11 for Prewitt and 7 by 7 for Sobel is used. It works by calculating the gradient of image intensity at each pixel within the image. The main advantage of these methods is that they are relatively simple in computation. But they have following disadvantages as they are directional, sensitive to noise, corners are often missed and the response to a step edge is across several pixels, so a post-processing is needed for "edge thinning".

    
    
### *Laplacian of Gaussian filter*
<p align="justify">
    Laplacian of gaussian is edge detector that is used to detect edges in both horizontal and vertical directions. It easily detects edges and it has fixed characteristics in all direction. It fails to function properly at the corner, curves and where the gray level intensity function varies.

### *Derivative of Gaussian filter*
<p align="justify">
    Derivative of gaussian is also directional edge detector that is used to detect edges in either horizontal or vertical direction. As derivatives are very sensitive to noise so First it smooths the images and then apply derivative to detect edges. The main advantage of derivative of gaussian, it is robust in noisy image. But it has following disadvantages as it is directional and post-processing is needed for "edge thinning" as the response to a step edge is across several pixels.

### *Canny Edge Detector*
<p align="justify">
    Canny edge detector is also used to detect edges in both directions. I used Otsu's thresholding in canny detector as it performs automatic image thresholding. Canny edge detector has better detection specially in noise condition. It uses probability for finding the error rate, localization and response. But it has complex computation and false zero crossing as well.

## 3. Image Sharpening Filter

### *Using Laplacian and Average Smoothing filters*
<p align="justify">
Image Sharpening is used to obtain fine detail such as lines and edges and remove blurred in an image. First of all, Laplacian which is a derivative filter is used as a high pass filter so it highlights the edges and lines in an image but derivative filters are sensitive to noise so it will also amplify the noise. This filter is applied on noise free image as its sensitive to noise. 
<p align="justify">
Another way to obtain a sharpen image by using low pass filter as it used unsharp mask. First it blurred the image and subtract it from original image to produced an unsharp mask then this unsharp mask is added to original image to produce sharpen image.
