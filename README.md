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
![Hardware](https://user-images.githubusercontent.com/65292012/118792763-41002380-b898-11eb-965f-4e1a38540268.png)

## Software Architecture
![sw esquema](https://user-images.githubusercontent.com/65292012/118792813-4c534f00-b898-11eb-949b-dbbe1c49e3cd.png)

## Extra components and 3D pieces

## Code dependencies

## Simulation Strategy

## References



