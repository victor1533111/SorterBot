# SorterBot 

## Table of contents

## Repository Introduction
This repository contains all the software modules, all the 3d files and the scenarios that make up our robotics project.
The available code and the 3d designs have been designed by the members of the RPL 2020-2021 group of computer engineering of the UAB formed by Cristian Gutiérrez, Carlos Peña and Víctor Batista and directed by the tutors Luis Vilariano and Carlos García.

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
 <img width="600" height="600" src="https://user-images.githubusercontent.com/65292012/118792813-4c534f00-b898-11eb-949b-dbbe1c49e3cd.png">
 </p>
  

## Code dependencies

-Tesseract OCR (You can find it inside the code folder)

-OpenCV

-Jupyter

-CoppeliaSim

* ## Instalation and uses

## Simulation Strategy and implementation


## Authors

## References

[1] FANUC America Corporation (16 mar 2018). High Speed SCARA Robot for Pick & Place [YouTube]. https://youtu.be/-m1oKuFkSTE

[2] How to Control Vacuum Pump Air Pump Suction for Robotic Arm (January 30, 2021). [Web Page]. https://create.arduino.cc/projecthub/ronfrtek/how-to-control-vacuum-pump-air-pump-suction-for-robotic-arm-5de318

[3] Armesto, L. (12 feb 2020). Cómo Usar los Sensores de Proximidad para Permanecer entre Paredes [YouTube]. https://youtu.be/j4dMnAPZu70

[4] Gitau, C. (2020, 11 enero). Fuzzy String Matching - Towards Data Science. Medium. https://towardsdatascience.com/fuzzy-string-matching-in-python

