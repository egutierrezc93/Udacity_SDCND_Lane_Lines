# **Finding Lane Lines on the Road** 

### Reflection

### 1. My pipeline.

My pipeline consisted of 7 steps. 

   First, I defines all the parameters for the transformations and converted the images to grayscale, 
   
   Second, I applied a Gaussian smoothing to the image to get better results in the Canny edge detection
   
   Third, I used the canny edge detection
   
   [//]: # (Canny edge image)

   [image1]: ./test_images/solidWhiteRightCannyEdges.jpg "Canny edge image"

   Then I got the Hough lines from the edge detected in the grayscale image
   
   [//]: # (Hough lines image)

   [image2]: ./test_images/solidWhiteRightHoughLines.jpg "Hough lines image"
   
   I extrapolated the lines detected to print only the two lane lines
   
   Finally I mix the original image with the lines
   
   [//]: # (Mixed image)

   [image2]: ./test_images/solidWhiteRightHoughLines.jpg "Mixed image"
   
In order to draw a single line on the left and right lanes, I modified the draw_lines() function to get an average slope and intercept for the left and right lanes, and setting the Y extreme points of my interest region I got the X points for the lane lines and draw them.


### 2. Potential shortcomings with my pipeline


One potential shortcoming would be what would happen when there is a curve in the image, thats a really great problem because I am assuming that the lane lines are always straight, and I have a static interest region too.

Another shortcoming could be when there is a car (or another object) near ahead of my camera, my pipeline would detect this car lines and get confused.


### 3. Possible improvements to my pipeline

A possible improvement would be to extrapolate the lane lines as a curve.

Another potential improvement could be to identify objects near my car and obviate their hough lines.
