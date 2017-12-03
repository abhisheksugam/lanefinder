#**Finding Lane Lines on the Road** 

##Writeup Template

###You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consists of five steps which are as follows:

1) Convert image into grayscale
2) Apply Gaussian smoothing to grayscaled image
3) Run Canny Edge Detector
4) Create a trapezoidal region-of-interest 
5) Apply Hough Line Transform
6) Filter Hough lines by slope and separate them into right/left lane line segments by identifying the most dominant line based on it's length for both left and right side. Then calculate the slope and intercept of the both lines using polyfit. Determine the end points of the single right and left line using the slope and intercept. 
7) The start and end points of the dominant line on the left and right are averaged with a moving average from the last 25 video frames.


###2. Identify potential shortcomings with your current pipeline

My current pipeline might fail in the following circumstances:
1) Night time or sunny days during which it becomes difficult to identify yellow lanes
2) During bad weather (snow or rain)
3) While passing under the bridge or in shadows or trees, advertisement board etc.


###3. Suggest possible improvements to your pipeline

Some improvements that can made to my pipeline are as follows:
1) Fine tuning the parameters for the hough transform or canny edge detection to make it work in sunny days, night time or in bad weather conditions
2) The pipeline was only tested when there is no traffic. It would be interesting to see how it behaves in heavy traffic and improvements can be made to make it more robust.