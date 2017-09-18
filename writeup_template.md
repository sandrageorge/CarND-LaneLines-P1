# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images/solidYellowCurve.jpg "Example"
[image2]: ./test_images/output/grayScaleImage.jpg "Grayscale"
[image3]: ./test_images/output/edgeImage.jpg "edgeImage"
[image4]: ./test_images/output/ROIImage.jpg "ROIImage"
[image5]: ./test_images/output/output.jpg "output"

---

### Reflection

### 1. To describe the pipline used to detect lanes, let's use the image below as an example

![alt text][image1]

My pipeline consisted of 5 steps. First, I converted the images to grayscale, 

![alt text][image2]

then used Gaussian for smothing and Canny for edge detection

![alt text][image3]

then selected the region of intrest by using region of intrest mask 

![alt text][image4]

then Hough transform is used to detect lines in the images.

![alt text][image5]

In order to draw a single line on the left and right lanes, I modified the draw_lines() function 
by getting the lines slopes and separate right and left lines according to the splote sign, add a threshold for the accepted slopes 
and make sure the 2 points constructing the line lie in the same half of the image (right or left)
Fit all right lines into one line and also for the left lines.


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the road is curved 

