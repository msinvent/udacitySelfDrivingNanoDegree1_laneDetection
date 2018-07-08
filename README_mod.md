# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images/solidYellowLeft.jpg "Original"
[image2]: ./test_images_output/YCrCb/output_solidYellowLeft.jpg "YCrCb"
[image3]: ./test_images_output/layer0/output_solidYellowLeft.jpg "Layer 0 of YCrCb"
[image4]: ./test_images_output/canny/output_solidYellowLeft.jpg "Canny Detected Edges"
[image5]: ./test_images_output/ROI/output_solidYellowLeft.jpg "Edges in ROI"
[image6]: ./test_images_output/rightAndLeftLanes/output_solidYellowLeft.jpg "hough lines followed by merging to find final lanes"
[image7]: ./test_images_output/output_solidYellowLeft.jpg "Detected Lane Edges"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps :
![alt text][image1]
#### a. Converted the images to YCrCb image
![alt text][image2]
#### b. Extracted Y layer of YCrCb image
![alt text][image3]
#### c. Applied canny edge detection on this layer.
![alt text][image4]
#### d. Removed edges outside the Region of Interest (ROI)
![alt text][image5]
#### f. Used hough transform to detect the straight lines in the image(did a lot of manual tuning here).
#### g. Merged all the hough lines to only two line, one on the left and other on the right of the lane. I have introduced this change in the hough_lines method directly, so it is returning only two lines.
![alt text][image6]
![alt text][image7]
####Note : Special care have been taken inside the methods draw_lines to make sure the code takes care of situation when no lane is detected


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
