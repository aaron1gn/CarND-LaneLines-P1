\#**Finding Lane Lines on the Road** [![Udacity - Self-Driving Car NanoDegree](https://camo.githubusercontent.com/5b9aa393f43d7bb9cc6277140465f5625f2dae7c/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f756461636974792d7364632f6769746875622f736869656c642d6361726e642e737667)](http://www.udacity.com/drive)

[![Combined Image](https://github.com/huangchiye/Udacity-CarND-LaneLines-P1/raw/master/laneLines_thirdPass.jpg)](https://github.com/huangchiye/Udacity-CarND-LaneLines-P1/blob/master/laneLines_thirdPass.jpg)



**Finding Lane Lines on the Road**

The goals / steps of this project are the following:

- Make a pipeline that finds lane lines on the road
- Reflect on your work in a written report

------

### Reflection

### Description

The image pipeline consists on 6 steps:

**Image Pipeline step 1: Converting images into gray scale**
def grayscale(img)
Input original image using cv2.cvtColor (BGR) method and returns a gray scaled image.

**Image Pipeline step 2: Applying Gaussian smoothing**
def gaussian_blur(img, kernel_size)
Applies a Gaussian blur to smooth image using cv2.GaussianBlur method

**Image Pipeline step 3: Applying Canny transform**
def canny(img, low_threshold, high_threshold)
Detect edges on the image using Canny function.

**Image Pipeline step 4: Applying Region of Interest**
def region_of_interest(img, vertices)
Masks the image segments that are not interesting in regards to the line detection.

**Image Pipeline step 5: Applying Hough transform**
def hough_lines(img, rho, theta, threshold, min_line_len, max_line_gap)
Filtering left and right lanes on the region of interest using Hough transform.

**Image Pipeline step 6: Optimizing finding lane lines **
def draw_lines(img, lines,color, thickness,line_length_coefficient)
Improving draw lines function by applying optimized left and right solid lines in the image, instead of segment short lines.

**Image Pipeline step 6: Merging original image with Hough transform image**
def weighted_img(img, initial_img, α=0.8, β=1., γ=0.)
Merges the output  image of hough transformation with the original image to represent driving lanes.

![](https://github.com/aaron7yi/CarND-LaneLines-P1/blob/master/6.png?raw=true)

### Potential shortcomings / Possible suggestions

- Better parameter set for the hough transformation
- Create a more robust algorithm that is able to adapt to more complicated scenarios.

<img src="https://github.com/aaron7yi/CarND-LaneLines-P1/blob/master/challenge_video.png?raw=truechallenge_video.png" alt="challenge_video" style="zoom: 25%;" />



