# edgedetection-roadlane
semester 7 project OUC Computer vision

### Problem:

In this work, we aim to detect lines, in video and also show the curves of the lines in applying our lane line detection. We also aim to provide road instructions to users of our system such as keep straight, go left as a proposal for assisting road users with lane change warning and detection. in our solution, we used a static image of our road first to explain the relative steps taken to get to the final result and then applied a video input for the final presentation since it is more useful.

### Algorithm:

* The process of lane line detection can be divided into the following steps:
  * Distortion correction
  * Separating red and yellow lines
  * Getting the bird's eye view using homography
  * detecting lanes in the image
  * filling the detected area with a certain color so driver can see clearly the path to follow
  * Radius of curvature
  * Turn prediction
 
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
in road lane detection, we are only intrested in a certain defined region of the image .
 * inorder to find this region of interest(ROI), we need our special points and crop the unnecessary ones accordingly.
 * we leave only the ROI and cover the useless parts
 * <img width="537" alt="roi" src="https://user-images.githubusercontent.com/56553042/147899919-2a7385c0-0aea-4e2c-88d5-5613158abca3.png">
 * below is the result of the masked image
<img width="960" alt="masking" src="https://user-images.githubusercontent.com/56553042/147899992-6e42426e-3c71-4723-8545-981882af70c7.png">
 * 
  * Lane lines have always been painted yellow and white for humans to see and follow while driving. 
  * we had to convert color space to make yellow and white clearly distinguished
  * we then performed HSL conversion of the images and we created 2 marks for the 2 colors.
  * we marked separately bit wise with the actual frame of the image.
  * afterwards we had to combine them and filter the noise.

#### Getting the bird's eye view using homography
