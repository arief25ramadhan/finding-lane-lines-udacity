# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals/steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps, which are:
<ol>
 <li>Convert the images into grayscale</li>
 <li>Perform Gaussian Blur to increase smoothness</li>
 <li>Perform Canny edge detection on the smoothed images </li>
 <li> Draw hough lines on the image while also determining the region of interest. Use the "bitwise and" operator</li>
 <li>Draw the constructed hough line on top of the original image to simulate lane detection</li>
 </ol>

For the optimization step (section 3), I  add make_coordinates, average_slope_intercept, and display_lines functions to draw smooth continuous lines on the detected right and left lanes.

### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming that my pipeline has is the inability to detect lanes in images with different sun/light intensities. The variation of light intensity will affect the Canny edge detection, which consequently messes up our lane finding.

Another possible shortcoming happens in detecting curved lines. From the "display_line" function, we can see that our algorithm can only draw a straight line by connecting two points. 


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to modify the above pipeline to detect the curved lane line. To do this, we need to consider more parameters and perform more advanced modeling of the problem.

We also have not explored different color spaces. We should decide which color space is the most suitable for extracting the lines by analyzing other color spaces in future works.