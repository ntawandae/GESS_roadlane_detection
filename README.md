# edgedetection-roadlane
semester 7 project OUC Computer vision



### Problem statement

Lane detection was developed based on traditional deep learning-based methods for detection, however these methods are no longer accurate and compatible to be applied in our today’s automobile industry.

Illustrated below are the drawbacks associated with these traditional methods which we are working on to improve them by applying advanced computer vision technology used in this project .

To address problems such as low detection accuracy of traditional methods and poor real-time performance of deep learning-based methodologies, we have decided to work on a lane detection algorithm for intelligent vehicles in complex road conditions and dynamic environments that can be applied in our today’s real world automobile industry, there is need for much more accurate methods to reduce car accidents as well as safety for our transport system .

Poor methods of traditional deep learning based methods had poor real time, this will make it difficult to apply such methods in our real world automobile industry since there is need for more accuracy inorder for this system to work properly .

After taking a thorough investigation on traditional deep learning based methods, we realized that, there is poor detection efficiency, therefore this method can not be applied to our real world automobile industry because we need good detection efficiency for our vehicles to operate smoothly without any car accidents 
[[1.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6679325/)]

~**Reference** :        https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6679325/~


### Objective

* _**Accuracy:**_
 The main purpose for developing this project is to reduce traffic accidents , so accuracy is our primary objective for this system design 
 If an error occurred in detection of the lane , it may cause a car togo to the wrong diretion , this will not be conducive to safety and risks of accidents might arise.

* _**High efficiency:**_
When the vehicle is driving on the road, it must not only be able to accurately follow the direction of the lane line but also be able to maintain a certain speed. 
For this systm to work, we need more accuracy and in realtime 

* _**Memory:**_
In the intelligent public transport system, in addition to the vehicle that can detect the lane line image in real time, it also has a good memory function, which can effectively store and manage the recorded data information and facilitate investigation and evidence collection after a traffic accident.

* _**Simple design structure:**_
The system design is mainly used in vehicles, and the occupied space should be as small as possible. To to access all features you can make full use of 5G communication real-time connection without affecting other functions of the vehicle.

* _**Fully automated:**_
We will design our system in such a way that it will allow the driver to alert and correct the driver’s driving errors in an unconscious situation, so it is necessary to be able to fully automate the system during operation.

**Reference**

[[2.](https://www.analyticsvidhya.com/blog/2020/05/tutorial-real-time-lane-detection-opencv/)]

[[3.](https://jivp-eurasipjournals.springeropen.com/articles/10.1186/s13640-018-0326-2)]

[[4.](https://www.sciencedirect.com/science/article/pii/S2095756420301458)]



### History and Background

In 2016, WHO estimated China had a total of 256,180 estimated road fatalities and 3,842,700 estimated serious injuries due to road accidents, some of these attributed to bad weather, or bad tailgating leading cars, which resulted in an estimated total Cost of $688,150 million for fatalities and Serious Injuries, 2016.
[[5.](https://www.roadsafetyfacility.org/country/china)]

These road traffic injuries bring considerable economic losses to victims, their families, and nations as a whole, Because of this we think that auto mobile cars developed with lane departure warnings or lane line detection systesm are a key fundamental to road safety.
In recent years, advanced driver assistance systems (ADAS) and autonomous driving cars have become more and more important in reducing traffic accidents.
Road lane line detection is a key instrumental technology for smart vehicles, and has attracted widespread attention since 2001 from plenty of big institutes and automobile technology companies, small institutions haven't had the opportunity of implementing this.
[[6.](https://en.wikipedia.org/wiki/Lane_departure_warning_system)]

Lane lines have always been painted for humans to see and follow while driving. In a very similar way, an autonomous vehicle that uses human designed infrastructure, needs to see the lane markings to steer accordingly and follow the road trajectory as these cars use the same roads as manually driven cars. The concept of LLD is used to describe the path for self-driving cars and to avoid the risk of getting in another lane.
Most previous research works could only detect lanes on non-curved roads, and lack of distinctive features on roads make lane detection algorithms seem ineffective and confused by other objects with similar appearance. Moreover, the inability to decipher faded, missing, or incorrect lane markings. Markings covered in snow or old lane markings left visible, inconsistent number of lanes on a road as well as diverse lane line patterns, e.g. solid, broken, single, double, merging, and splitting lines further hamper the performance.
[[7.](https://en.wikipedia.org/wiki/Lane_departure_warning_system#cite_note-missing-30)]

in our research, we will put into cinsideration the existance of curved roads, shadows, inconsistant continuous and discontinuous lanes with different colors.



### Approach/Methodology

**Our approach is as follows;**

*	Our first step will be to take an original image of the lane lines and we use python code and Open CV in our project to achieve our goals.
*	Our line detection device will be on the car’s dashboard for easy access when driving.So some roads are clear while some roads will not be clear because of atmospheric conditions for example when it’s rainy the lanes are not clear and when it’s at night.So what we will do is to clear our image by using Gaussian blur to remove noises in our image and to make sure that all the objects that are appearing on the picture are relevant to our task if they are not we clear them.
*	After removing the noise we will delete all the colors in our image.This will help us see which objects have higher brightness than the others because when there is color it’s not clear.
*	After deleting the colors we will have to detect the edges and we will use canny to detect the edges.When detecting the edges we use our grayscale image and since we  will remove the noise and erase some unnecessary objects. The edges that will be detected mostly are the lane lines and the other objects around.The colors are changed to black and white.To clearly show the detected edges.
*	After detecting the edges we will then cut out all the other objects and noise in our images like the surrounding trees or buildings and we will be left with the lane lines which is our main target in this project.and we use a shape bounded by two lines and we call it a polygonal shape since the lanes change their shape.They are no always straight.
*	We will draw the lines and we make them thick and more clear and we use the draw lines function to draw them.
*	We will use a method of detecting lines called the Hough Transform.This will help us to detect the lane lines on a road.
*	Hough Transform will detect some lines but however it can output several output lines and we have to leave one line of best fit that will represent our lanes and we use an equation to find the gradient or the slope line to achieve that.When the gradient of the lines are positive it is for the left lane and when the gradient is negative it is for the left lane.[[11.](https://towardsdatascience.com/advanced-lane-detection-for-autonomous-vehicles-using-computer-vision-techniques-f229e4245e41?gi=d317808a7d49)]
*	And now we have different slope lines on the left lane and the right lane and we have to remove the other slope lines to remain with the best slope lines that can be used and to achieve that we use the reject outliers function that will reject all the surrounding lines and leave the best fit lanes.
*	We will have to find a straight line that best approximates the two lane points and to achieve that we use linear regression function.
*	The last step is to output the final image with the lanes drawn.We have to set our detected lines in our original image and they should be visible and be able to detect the lanes.
This project will be mainly for people who own cars.So when we finish our program we will ask people with cars to test our program in their vehicles . After giving them we will then give them a questionnaire for them to rate our program. They will also tell us how we can improve our system.

### REQUIREMENTS

Inorder to implement the project, the following conditions are required 

*	Jupyter Notebook
*	Shell
*	Opencv for Python 
*	Ubuntu Linux version 11.10
*	Apache web Server version 2
*	Windows 7+ 
*	Processor 1.8GHz 

NB; All the stated resources are on open source and free to download

### REFERENCES:

1. https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6679325/ 
2. https://www.analyticsvidhya.com/blog/2020/05/tutorial-real-time-lane-detection-opencv/
3. https://jivp-eurasipjournals.springeropen.com/articles/10.1186/s13640-018-0326-2
4. https://www.sciencedirect.com/science/article/pii/S2095756420301458
5. https://jivp-eurasipjournals.springeropen.com/articles/10.1186/s13640-018-0326-2
6. https://en.wikipedia.org/wiki/Lane_departure_warning_system
7. https://en.wikipedia.org/wiki/Lane_departure_warning_system#cite_note-missing-30
8. Andrés F. Cela , Luis M. Bergasa, Franklin L. Sánchez and Marco A. Herrera, “Lanes Detection Based on Unsupervised and Adaptive Classifier”, 978-0-7695-5042-8/13 $26.00 © 2013 IEEE.
9. M. Aly, "Real time detection of lane markers in urban streets," IEEE Intelligent Vehicles Symposium, pp. 7-12, June 2008.
10. ZuWhanKim,Member,IEEE, “Robust Lane Detection and Tracking in Challenging Scenarios”, IEEE transactions on intelligent transportation systems, Vol. 9, No.1, March 2008.
11. https://towardsdatascience.com/advanced-lane-detection-for-autonomous-vehicles-using-computer-vision-techniques-f229e4245e41?gi=d317808a7d49
