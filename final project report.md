# edgedetection-roadlane
semester 7 project OUC Computer vision

### Problem:

In this work, we aim to detect lines, in video and also show the curves of the lines in applying our lane line detection. We also aim to provide road instructions to users of our system such as keep straight, go left as a proposal for assisting road users with lane change warning and detection. in our solution, we used a static image of our road first to explain the relative steps taken to get to the final result and then applied a video input for the final presentation since it is more useful.

### Algorithm:

* The process of lane line detection can be divided into the following steps:
  * Distortion correction/Denoising the image
  * detecting lanes in the image
  * (ROI) Region of Interest 
  * Line Detection
  * Left and Right lines separation
  * Display Complete Lines
  
#### 1. Gaussian Blur
* First we had to remove the distortion(noise) from the image and then smoothen the image
  * we used opencv to operate the function and a kernel matrix of a sprcific size(5x5), and a deviation using the gaussian blur
  * gradient, is a change in brightness over a series of pixels
  * here are the functions we used to remove noise
    
#### 2. Canny Edge Detection
* secondly, we had to do edge detection which is an algorithm to detect edges in our image. 
* changing the intensity of pixels will give us an edge.
  * before detecting edges we had to convert our image to grayscale image using the cv2 function cvtColor().
  * we then had to binarize the image by applying thrshhold technique. if gradient is larger than *_high threshold_* then it is accepted as an edge pixel. and if below the *_low threshold_*, it is rejected.
  * we use the canny technique to detect images: below is the cany technique code and the resulting image after canny:

 ![canny](https://user-images.githubusercontent.com/56553042/147899374-6ab1bafb-8f87-4a59-ad46-5639252807b5.png)
 
#### 3. Masking the image
* in road lane detection, we are only intrested in a certain defined region of the image .
 * inorder to find this region of interest(ROI), we need our special points and crop the unnecessary ones accordingly.
 * we leave only the ROI and cover the useless parts
 * <img width="537" alt="roi" src="https://user-images.githubusercontent.com/56553042/147899919-2a7385c0-0aea-4e2c-88d5-5613158abca3.png">
 * below is the cropped image:
 * <img width="960" alt="cropped" src="https://user-images.githubusercontent.com/56553042/147901965-36c5b508-a258-44da-9a23-d50e343d895f.png">
 * below is the result of the masked image
<img width="960" alt="masking" src="https://user-images.githubusercontent.com/56553042/147899992-6e42426e-3c71-4723-8545-981882af70c7.png">
 
#### 4. Line Detection by Hough Transformation
 
* we used the hough transformation technique to detect and generate straight lines in the image. 
* the equation of a straight line can be given as **y=mx+c**, where m is the *_slope_* and c is the *_y-intercept_*
  * we can transform everyline from 2d space (x vs y) to the hough space (M vs C).
  * a single point in 2d space can be represented by a line in hough space.
  * to apply this technique, the following code was applied
  * <img width="551" alt="line sep" src="https://user-images.githubusercontent.com/56553042/147901034-b32d7f58-eef2-459f-934b-699f6903118d.png">
  * <img width="355" alt="houghtransform" src="https://user-images.githubusercontent.com/56553042/147900554-66cbe03e-3276-46ce-b213-67c9919d1e91.png">
  
#### 5. Left and Right lines separation
 * a slope helps us identify which points are on the left or right
  * in order to draw the continuous line, we had to find averages of these left or right point arrays.
  * for making coordinates,we define a function which help us to make coordinates for the line with the given slope and intercept:
<img width="252" alt="lrseparation" src="https://user-images.githubusercontent.com/56553042/147901035-1c40b5f8-3456-4559-9d18-f4000131db45.png">
<img width="370" alt="rlseparation" src="https://user-images.githubusercontent.com/56553042/147901036-bf0e9d19-9956-49bb-a13c-5a5266eae05c.png">

#### 6. Display Complete Lines
* to draw the lines use the function display_lines
* it takes the argument image and averaged lines with defined points and draws using cv2.line() function:
*  <img width="535" alt="displaylines" src="https://user-images.githubusercontent.com/56553042/147901390-7d697439-fa96-45d1-aab0-62a80f37e6d9.png">
 * below is an image result after applying left and right line separation:
  <img width="960" alt="lineseparation" src="https://user-images.githubusercontent.com/56553042/147901133-32e95536-fc72-4c55-8dfd-c786bfa7ba36.png">
and below is the final image after all the processes have been done:
<img width="960" alt="finalimage" src="https://user-images.githubusercontent.com/56553042/147901613-c857fb9a-a45e-457a-8fc9-c00bdc1f23a2.png">
