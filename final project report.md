# edgedetection-roadlane
semester 7 project OUC Computer vision

Problem:

In this work, we aim to detect lines, in video and also show the curves of the lines in applying our lane line detection. We also aim to provide road instructions to users of our system such as keep straight, go left as a proposal for assisting road users with lane change warning and detection.

Algorithm:

The process of lane line detection can be divided into the following steps:
Distortion correction
Separating red and yellow lines
Getting the bird's eye view using homography
detecting lanes in the image
filling the detected area with a certain color so driver can see clearly the path to follow
Radius of curvature
Turn prediction
