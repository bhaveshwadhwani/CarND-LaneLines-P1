<<<<<<< HEAD
# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)


Output
---
<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />

Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

In this project we will detect lane lines in images using Python and OpenCV.  OpenCV means "Open-Source Computer Vision", which is a package that has many useful tools for analyzing images.  

For the project, two files are submitted: a file containing project code and a file containing a brief write up explaining the solution. The [code](https://github.com/bhaveshwadhwani/CarND-LaneLines-P1/blob/master/P1.ipynb) and the [writeup](https://github.com/bhaveshwadhwani/CarND-LaneLines-P1/blob/master/writeup.md).The code file is called P1.ipynb and the writeup template is writeup_template.md 

To meet specifications in the project, take a look at the requirements in the [project rubric](https://review.udacity.com/#!/rubrics/322/view)


Please read Writeup for better understanding of process for line detection .
---
Link for [writeup](https://github.com/bhaveshwadhwani/CarND-LaneLines-P1/blob/master/writeup.md)

Description of Pipeline in Writeup

My pipeline consists of 6 steps.  
1) Graysale image
2) Gaussian blur
3) Canny Edge Detction
4) Region of interest
5) Hough lines & Drawing edges to lanes
6) Combining input and output image


The Project
---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road .
* Reflect on your work in a written report .


>>>>>>>>>>
