# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:

* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Pipeline Description

My pipeline consisted of these steps; first, I converted the images to grayscale and smoothed them using gaussian blur to prepare them for the edge detection. The result was used in the Canny edge detection after deciding what the low- and high-threshold should be. After that we needed to look at our region of interest by masking the section where the lane lines are most likely to be. The masked section is hough transformed to pick out lines. We seperated all those lines into two groups; the left and right lane. We can do that by calculating the slope and intercept of the lines. A negative slope for the left lane and a positive slope for the right lane. This is where the draw_line function should be modified. First, I inserted a for loop to loop over the coordinates. Second, I calculated the m and b value. Now depending on the m value I stored the values in the Left or Right lane list. When those two lists are made we calculate the mean of the line values m and b to generate the full line.
 



### 2. Potential shortcomings with current pipeline


One potential shortcoming would be what would happen when the lane lines have a color similar to the road, the edges won't be detected as good in that case. There could also be problems in tight turns, I don't think calculating the slope will do the job in that case. A big improvemt is to allow for it to read curves in order to predict the upcoming turns.

