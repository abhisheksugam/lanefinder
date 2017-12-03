#**Finding Lane Lines on the Road** 

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consists of the following steps:

1) Convert image into grayscale
2) Apply Gaussian smoothing to grayscaled image
3) Run Canny Edge Detector
4) Create a trapezoidal region-of-interest 
5) Apply Hough Line Transform
6) Filter Hough lines by slope and separate them into right/left lane line segments by identifying the most dominant line based on it's length for both left and right side. Then calculate the slope and intercept of the both lines using polyfit. Determine the end points of the single right and left line using the slope and intercept. 
7) The start and end points of the dominant line on the left and right are averaged with a moving average from the last 25 video frames.


###2. Identify potential shortcomings with your current pipeline

My current pipeline fails for the optional challenge video, this might be due to many reasons such as:
1. uneven color of the road
2. navigating around a curve
3. shadows might interfere with the pipeline
