# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals of this project are the following:
* Detect lanes on test images and videos while driving on the highway under reasonably well lighting conditions
  * No snow on the road
  * No rain
  * Some shadows from trees and other objects are acceptable

---

### Reflection

### 1. The Pipeline.
My pipeline consists of two main steps: 
a. Identifying lines 
This workflow further consists of several steps. Initially I tried converting the images to grayscale followed by Gaussian blurring and then Canny edge detection followed by Hough transform to get detect the lanes. This method worked well when the lighting was good - meaning no shadows or other discolouration. Also, this procedure worked well for all white lines. But in cases where there are shadows or for yellow lines, the process did not alwyas give good results. 

Image with shadow and yellow lane			       |	Grayscale
-------------------------------------------|-----------------------------------------
<img src="images/shadow.jpg" width="350">  |	<img src="images/gray.jpg" width="350">

To over come this, instead of grayscale, I converted the image to HSL colour scheme, which shows yellows much better even in shadows. 

Image with shadow and yellow lane			       |	HSL
-------------------------------------------|-----------------------------------------
<img src="images/shadow.jpg" width="350">  |	<img src="images/hsl.jpg" width="350">

This step is followed by Gaussian blurring kernel=15 to remove tiny features and then canny edge detection. The result is seen below. It is clear that the lanes are identified pretty well even with the shadow.

*Step a.1: Colour Selection*
<img src="images/colour_selected.jpg" width="500">

*Step a.2: Gaussian blurring*
<img src="images/gaussian_blur.jpg" width="500">

*Step a.3: Canny edges*
<img src="images/edges.jpg" width="500">

*Step a.4: Edges in region of interest*
<img src="images/region_of_interest.jpg" width="500">

*Step a.5: Hough lines*
<img src="images/combined.jpg" width="500">

*Step a.5: Final*
<img src="images/final.jpg" width="500">

b. Averaging the lines

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
