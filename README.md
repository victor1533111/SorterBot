
# SorterBot 

<p align="Left">
<img src="https://user-images.githubusercontent.com/65292012/118978363-847d8f00-b977-11eb-9f00-556dfbc2a6cb.gif" width="450" height="300"  />
 </p>



## Table of contents
* [Repository Introduction](#Repository-Introduction)
* [Video](#Video)
* [Code dependencies](#Code-dependencies )
  * [Instalation and uses](#Instalation-and-uses )
* [Project description](#Project-description)
* [Electronic components](#Electronic-components)
* [Hardware Scheme ](#Hardware-Scheme )
* [Extra components and 3D pieces](#Extra-components-and-3D-pieces )
* [Software Architecture ](#Software-Architecture )
* [Simulation Strategy and implementation ](#Simulation-Strategy-and-implementation )
* [Tests](#Tests)
  * [Title sorting test](#Title-sorting-test)
  * [Data sorting test](#Data-sorting-test)
  * [Sheet detection test](#Sheet-detection-test)
  * [Sheet Orientation test](#Sheet-Orientation-test)
* [Contributions](#Contributions)
* [Authors](#Authors )
* [References](#References)

## Repository Introduction
This repository contains all the software modules, all the 3d files and the scenarios that make up our robotics project.
The available code and the 3d designs have been designed by the members of the RPL 2020-2021 group of computer engineering of the UAB formed by Cristian Gutiérrez, Carlos Peña and Víctor Batista and directed by the tutors Luis Vilariano and Carlos García.

## Video


[![Video](https://img.youtube.com/vi/GDZ8xmWGUts/0.jpg)](https://www.youtube.com/watch?v=GDZ8xmWGUts)


## Code dependencies

-Tesseract OCR (pipenv , Pillow , pythonRLSA )

-OpenCV

-Jupyter

-CoppeliaSim

-Fuzzywuzzy


   * ## Instalation and uses
   The first thing to do is to install tesseract, to do this you have to access the code folder and run the tesseract application, once run just select the next option until the    last tab where you have to select finish. Important not to change the installation path since it will be the one used in the execution of the code.
   With respect to the rest of dependencies it is necessary to accede to the program and to change the second block of code of markdown to code and to execute it.
   Once the requirements have been installed, perform the following steps:
   1. Open the coppeliasim program with the scenario you wish to run. 
   
   2. Access the jupyter notebook and run all the blocks.
  
   3. A box with two buttons will appear, click the button depending on the scenario you have chosen.

## Project description
SorterBot is a pick and place robot that through the use of a hydraulic pump and a suction cup is able to perform two functionalities which are to classify subject notes by their title and to sort them by the relevant date that appears in those notes.
To perform the first functionality SorterBot implements computer vision by means of a camera that allows it to visualize the content of the notes. From the content it analyzes, it saves the information of the titles in order to classify them according to the subject to which they correspond. Also note that in case there are sheets that do not contain information on subjects or there are more subjects than available spaces, it classifies them in a separate set.
The second functionality, as we have already mentioned, allows us to organize the notes of a subject by dates. For this SorterBot uses computer vision that allows it to visualize the content of the notes from which it extracts the date that appears at the top of the sheet. Once the date is obtained, it uses the Hanoi algorithm with which it groups the sheets in different blocks depending on whether they correspond to an older or more current date in order to place them in an orderly fashion.
To highlight as contributions that It is a project that has a direct and wide application since it is automating a very frequent problem, the sorting of physical documents and their classification into different categories, thus allowing its use in any work or leisure environment and that Our robot differs from other pick & place robots[1] because it can apply different strategies and algorithms to classify and group documents. It should be noted that these strategies are based on the treatment of images of documents and on obtaining their information, thus allowing us to use it in any case where there is text, since it does not focus on the form but on the content.

## Electronic components
■ 1x Arduino

■ 1x Vacuum pump 

■ 1x Suction cup 

■ 1x Raspberry pi

■ 1x Raspberry pi camera 

■ 1x Power supply unit (8v) 

■ 3x Servomotor (1 x MG995 ->15kg, 2x MG90S -> 2,2kg) -> require de 4.8 a 7.3 v

■ 1x Infrared proximity sensor 

■ 1x Robot Skeleton

## Hardware Scheme 

<p align="center">
 <img  src="https://user-images.githubusercontent.com/65292012/118792763-41002380-b898-11eb-965f-4e1a38540268.png">
 </p>
 
## Extra components and 3D pieces
■ 2 Buttons

■ Body

■ Rotational arm

■ Proximity sensor holder

■ Prismatic arm

■ Flexible suction tube

■ Camera support

■ Suction tube storage and prismatic overlay (Vacuum zone)

■ Base arm support

■ 6 bars

■ Nuts and bolts

■ Servomotor Box

<p align="center">
 <img width="600" height="600" src="https://user-images.githubusercontent.com/65292012/118793111-9805f880-b898-11eb-924d-9e0c91551795.png">
 </p>

The main part of SorterBot is the body which apart from being an important part as far as the weight distribution of the structure is concerned, is the part where the vacuum pump and the robot's computers are kept, which in this case are the arduino and the raspberry pi.
In the body itself we find two buttons placed on its square base that allow us to select between the sorting algorithm (red button) and the organization (green button).
Next to this body we find a rotational arm connected by 4 bars that allows us to increase the mobilization of the body in the axis of the and, in addition to perform a 360 degree angle by means of the servomotor that is incorporated in the servomotor box located on top of the arm.
On top of this arm we find the piece that allows us to partially cover the prismatic arm as it moves along the z-axis, in addition to being the receiver of the flexible suction tube that is connected to the vacuum pump that goes from the base to the storage and generates the suction force of the suction cup [2]. It should be noted that this part allows us to create a vacuum zone.
Finally we find the camera support attached to the rotational arm and the proximity sensor support attached to the prismatic arm.
These two supports allow us in the first case to hold the camera of the raspberry pi perpendicular to the points, as well as to protect it and in the second case to place the sensor near the suction cup to calculate the distance to the object.


## Software Architecture
<p align="center">
 <img width="600" height="600" src="https://user-images.githubusercontent.com/65292012/118979839-3073aa00-b979-11eb-80d1-030a6b00e1c8.png">
 </p>
  
## Simulation Strategy and implementation

To simulate the project the first thing we do is to define the 3D design of the robot
using the TinkerCad application.
Once the design is done we export it in MTL format to be able to import it into the
Coppelia Sim platform keeping its colors.
In this platform we add the pertinent links that correspond to the servomotors of
our robot and we add a sensor to be able to visualize objects and another sensor to
detect the proximity[3] to these.
Once the robot is assembled we have defined several scenarios both for the
realization of the algorithms and for testing.
The first of them is a scenario in which we have defined a work table, a set of 6 file
cabinets that are at the following angles 45,90,-90,120,-120,150,-150,180, and a series
of sheets containing information of various subjects that are oriented at the zero
position of the robot.

<p align="Center">

<img width="400" height="250" src="https://user-images.githubusercontent.com/65292012/118979725-11751800-b979-11eb-81ad-5c93d13bfca4.png">
 </p>

These angles have been chosen because of the size of the sheets, otherwise the binders would collide.
Also note that the angle -45 is reserved for the orientation of the leaves, otherwise it could be the case that there are two leaves in which the top one is well oriented and the bottom one is badly oriented and consequently an erroneous calculation would be made as shown in the following image:

<p align="Center">

<img width="200" height="200" src="https://user-images.githubusercontent.com/65292012/118980137-77619f80-b979-11eb-99a2-95c18c6406aa.png">
 </p>
In this scenario the robot is responsible for performing the classification algorithm for which it takes each sheet independently by using the proximity sensor that allows us to stop the arm before colliding with the sheets,  and takes them to the orientation angle to see whether or not it is necessary to rotate them. Once the sheet is well oriented, the extraction of the text and identification of the title is carried out and then, by means of a strategy of percentage [4] of appearance and similarity of words, it is placed in a filing cabinet or other. If there is no subject associated with the sheet, an empty file cabinet will be found to place it, and if there are no file cabinets, it will be placed in the file cabinet located at 180 degrees.
Finally, add that the algorithm ends when it returns to the initial position and observes that there is no sheet of paper.

As a second scenario we have used the same as the previous one but in this case the sheets are already classified in their respective filing cabinets as shown in the following image:
<p align="Center">
 <img width="400" height="250" src="https://user-images.githubusercontent.com/65302766/119014737-8f94e700-b998-11eb-9f71-baca90708c64.png">
 </p>
In this scenario we perform the sorting algorithm for which the robot goes to each file cabinet, in a set order, and sorts the sheets by helping the two nearby file cabinets to perform the same.

The algorithm of sorting data is divided into two phases:<br />
1. Read dates: Reads all dates from the stack, storing in an auxiliary angle.<br />
2. Stack Sort Algorithm: Proceeds to sort the sheets, using a maximum of two binders and leaving them in a third one, which corresponds to the binder where the stack to be sorted was.

We make the abstraction of viewing the file cabinets with all their sheets as a stack with elements:
<p align="Center">
<img width="350" height="350" src="https://user-images.githubusercontent.com/65302766/119013207-10eb7a00-b997-11eb-99ed-f5b3560667ea.png">
<img width="350" height="350" src="https://user-images.githubusercontent.com/65302766/119014171-fcf44800-b997-11eb-86e0-70f09280ec8c.png">
 </p>

## Tests
To test the different algorithm modules of the Sorterbot, we have created 3 different scenarios and 4 different test.
 * ## Title sorting test
In this scenario we have a series of sheets with titles with different characteristics such as different sizes, numbers, strange symbols... In this case the scenario that we use is the second scenario and it is used to perform the title test in which the correct extraction of these titles will be checked with the corresponding elimination of elements that do not provide information. To evaluate the robustness of this title, the comparison of similarity with the correct titles is applied to make the sum of the percentages of similarity error.

It should be noted that the results obtained for this test have a 1.5 percent error rate.
 * ## Data sorting test  
 
The test itself consists of storing the result of the sorting in a list along the total sorting of all file cabinets.
Finally it is compared with the expected result to see if the sorting has been done correctly.
This test is useful to detect errors in the camera, the sorting algorithm and the general and functional operation of the MVP.
As a result, we have obtained the correct identification and conversion of all the dates

 * ## Sheet detection test
This test is performed in scenario 2 aswell.
The purpose of this test is to check that when there is an empty tray, the robot ignores this tray and continues with the sorting.
As results we have not obtained any problem in this test and its correct resolution has been performed.
 * ## Sheet Orientation test
In this case the test belongs to the third scenario which consist in only one filing cabinet in position -90 and a pile of misguided sheets as shown in the following image:
<p align="Center">
<img width="400" height="250" src="https://user-images.githubusercontent.com/65302766/119017106-f0252380-b99a-11eb-8a31-9ce6c2cbdb88.png">
</p>
In this scenario we test the orientation algorithm for which the robot picks a sheet from the origin pile, then it moves it to orientation -45 where aren’t any noises, there the camera takes a photo of the sheet. Finaly we use computer vision techniques to take the longest line in the image corresponding to the sheet’s heigh, we detect angle of that line and then we proceed to correctly orientate it and place it in the filing cabinet.


The test consists in calculate the total error, the sum of the absolute error of all the sheets after being properly orientated.


<img width="400" height="400" src="https://user-images.githubusercontent.com/65302766/119017392-409c8100-b99b-11eb-9bbd-1718b3decb79.png">


As we can see, in a sample of 20 sheets the sum of existing errors was below 1 degree.

## Contributions
This is open source, any contribution is welcome. 

## Authors
Víctor Batista Medeiros - <a href="https://github.com/victor1533111">Github</a>

Carlos Peña de Pedro - <a href="https://github.com/CarlosPenaDePedro">Github</a>

Cristian Gutiérrez Gómez - <a href="https://github.com/cristiangutierrz">Github</a>

## References

[1] FANUC America Corporation (16 mar 2018). High Speed SCARA Robot for Pick & Place [YouTube]. https://youtu.be/-m1oKuFkSTE

[2] How to Control Vacuum Pump Air Pump Suction for Robotic Arm (January 30, 2021). [Web Page]. https://create.arduino.cc/projecthub/ronfrtek/how-to-control-vacuum-pump-air-pump-suction-for-robotic-arm-5de318

[3] Armesto, L. (12 feb 2020). Cómo Usar los Sensores de Proximidad para Permanecer entre Paredes [YouTube]. https://youtu.be/j4dMnAPZu70

[4] Gitau, C. (2020, 11 enero). Fuzzy String Matching - Towards Data Science. Medium. https://towardsdatascience.com/fuzzy-string-matching-in-python

