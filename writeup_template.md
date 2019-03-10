# **Finding Lane Lines on the Road** 

## Writeup for Project Finding Lane Lines on the Road
---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)


[image1]: ./test_images/solidWhiteRight.jpg "Input"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consists of 6 steps.  
    1) Graysale image
    2) Gaussian blur
    3) Canny Edge Detction
    4) Region of interest
    5) Hough lines & Drawing edges to lanes
    6) Combining input and output image

First, Convert an image in Grayscale image to reduce burden on processor(as we will be dealing in live stream of data and for faster performance )
[image2]: ./examples/grayscale.jpg "Grayscale"
Then , we smoothen image with 5x5 Gaussian filter . We can pick diffierent values but 5 is bit standard value and it worked for me .

Internally Canny Edge Detection Algorithm also applies 5x5 Gaussian filter for smoothening but we did just to ensure there is less noise in data . Smoothened image is then filtered with a Sobel kernel in both horizontal and vertical direction to get first derivative in horizontal direction (G_x) and vertical direction (G_y).Gradient direction is always perpendicular to edges. Finding Intensity Gradient of the Image . Low threshold and high thresholds are taken , those who lie between these two thresholds are classified edges or non-edges based on their connectivity.

We then narrow down our region of interest so as to focus on edges of lanes and not on other edges. For this we use a simple trapezoidal mask and other than that region we take blank image .

Output from canny for the lane edges is given to hough transform for detecting lines edge points . 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by seperating line segments using values of slopes and filtered unwanted edges . Then fitting a line to all relevant lines on left and right . Finally we get a left and right line for lane .


Here is how an output image will look like after all this processing : 

[image3]: ./examples/output1_solidwhiterght.jpg "Output"


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be dealing with curved lines as we using a linear pattern for detection . For curved we will get distorted line for edges . 

Another shortcoming could be for images which are distorted or taking from an angle or view that can change shape of edges of line . This will have a negative impact on our output .


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to fit the output lines better so that curved lines can be detected .

Another potential improvement could be to clear distortion of images .
