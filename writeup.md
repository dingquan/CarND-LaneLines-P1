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


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
