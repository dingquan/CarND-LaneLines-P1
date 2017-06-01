# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of the following steps:

1. Convert the image to grayscale
2. Apply Gaussian blur and Canny edge detection
3. Use a Trapezoidal region to mask out regions that's irrelavent to the problem
4. Run Hough transformation of the masked image to detect lines
5. Iterate through the lines from step 4 and classify them as left lane lines (negative m) and right lane lines (positive m). Filtering out lines whose slopes are two flat or two steep. (keep the ones with slope between 0.5 and 0.8)
6. Calculate the intersection with the bottom of the image and draw the extrapolated lines.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline

1. haven't got around to stablize the lines by averaging the line positions across some number of frames 
2. the region of interest coordinates are hard coded which might not work for different videos

### 3. Suggest possible improvements to your pipeline

1. Have a buffer of 5 frames of images and average the line positions to reduce the flickering
2. In slack, Radu Prekup suggested finding the vanish point to filter out canny detected lines that are not part of the lane lines. I tried to use it in the challenge video using the suggested RANSAC regressor but haven't got it working properly yet.
