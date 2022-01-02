# edgedetection-roadlane
semester 7 project OUC Computer vision

### Problem:

In this work, we aim to detect lines, in video and also show the curves of the lines in applying our lane line detection. We also aim to provide road instructions to users of our system such as keep straight, go left as a proposal for assisting road users with lane change warning and detection.

### Algorithm:

* The process of lane line detection can be divided into the following steps:
  * Distortion correction
  * Separating red and yellow lines
  * Getting the bird's eye view using homography
  * detecting lanes in the image
  * filling the detected area with a certain color so driver can see clearly the path to follow
  * Radius of curvature
  * Turn prediction
 
#### Distortion correction
* First we had to remove the distortion from the image
  * we used opencv to operate the function 
  * here are the functions we used to remove distortion
    
#### Separating red and yellow lines
* secondly, we had to remove road lane markings of red and yellow lines.
  * Lane lines have always been painted yellow and white for humans to see and follow while driving. 
  * we had to convert color space to make yellow and white clearly distinguished
  * we then performed HSL conversion of the images and we created 2 marks for the 2 colors.
  * we marked separately bit wise with the actual frame of the image.
  * afterwards we had to combine them and filter the noise.

#### Getting the bird's eye view using homography
