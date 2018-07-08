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

My pipeline consisted of 5 steps :

#### a. Converted the images to YCrCb image
#### b. Thresholding the image in YCrCb space to find the white and yellow regions
#### c. Defined the ROI(region of interest), and, then removed the thresholded portion of the image that was not in the ROI.
#### d. Then I am using this 3 layer image to extract a single layer that represents the thresholded image.
#### e. Applied canny edge detection on this layer.
#### f. Used hough transform to detect the straight lines in the image(did a lot of manual tuning here).
#### g. Merged all the hough lines to only two line, one on the left and other on the right of the lane. I have introduced this change in the hough_lines method directly, so it is returning only two lines.

####Note : Special care have been taken inside the methods hough_lines and draw_lines to make sure the code runs even if no lines are generated.


If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
