# **Finding Lane Lines on the Road** 

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

My pipeline consisted of 6 main steps :
![alt text][image1]
#### a. Converted the images to YCrCb image
![alt text][image2]
#### b. Extracted Y layer of YCrCb image
![alt text][image3]
#### c. Applied canny edge detection on this layer.
![alt text][image4]
#### d. Removed edges outside the Region of Interest (ROI)
![alt text][image5]
#### e. Used hough transform to detect the straight lines in the image(did a lot of manual tuning here).
#### f. Merged all the hough lines to only two line, one on the left and other on the right of the lane. I have introduced this change in the hough_lines method directly, so it is returning only two lines.
![alt text][image6]
![alt text][image7]
#### g : Special care have been taken inside the methods draw_lines to make sure the code takes care of situation when no lane is detected


### 2. Identify potential shortcomings with your current pipeline

The current pipeline is definetly dependent on the brightness and it will be very hard to tune it for all the possible scenarios a real car will face if we go through this simple strategy. Moreover, we are detecting lanes by looking at each image frame individually and thus losing a lot of causal information that a video stream of road might have regarding the lane location.


### 3. Suggest possible improvements to your pipeline

An instantaneous and quick change might be to use the lane line locations from the previous frames to finalize the lane line location in the current frame. We can use it to atleast find unrealistic changes to flag a misinformation.
Another change may be to use data from different times of the day and different season to see if somekind of adaptive threasholding will be able to find a blanket solution for edge detection instead of simple canny.
