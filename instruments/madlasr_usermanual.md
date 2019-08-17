---
layout: single
title: MADLaSR User Manual
sidebar:
  nav: "side"
---
**Larry Gardner**  
*07/25/2017*  

*Please read all of this manual before operating the MADLaSR.*

## Contents:
1. **Installation Guide**
    - For first time users
2. **Instructions for APT user interface & PC-Solo Interface**]
    - For users who wish to control the MADLaSR without using the program to take data
3. **Instructions for LabVIEW program**
    - For users who wish to record data and conduct testing
4. **Warnings**
    - Important considerations for all users

## Installation Guide  
1. Install APT Setup Software. This can be downloaded from the Thorlabs website.  
2. Install PC-SOLO interface from within the `Gentec` files folder. (*This product has been discontinued and thus, these drivers are no longer publicly available. Must contact Gentec if interested in obtaining drivers*)  
3. Complete APT Configuration to ensure successful communication with linear actuators.  
4. Check PC-Solo and APT User Interfaces to see if hardware is properly functioning.  

## Instructions for APT User Interface & PC-Solo Interface
1. Plug in Gentec and Linear Actuators (LA's) to USB ports prior to starting APT User or PC-SOLO Interfaces.  
2. Open APT User Interface. If both LA's are connected to computer properly, two control panels should be displayed on the interface.  
3. Independent control is now granted for either LA.  
4. Open PC-SOLO Interface. From the `Serial Port` drop-down menu, select current port.  
5. Readings from the Gentec are displayed in real time as seen on the `devices` screen.  

## Instructions for LabVIEW Program
1. Plug in Gentec and Linear actuator's (LA's) to USB port prior to starting program. Turn on laser, LA's and Gentec.  
2. Open either black materials or white materials program. Open front panel if not already displayed.  
**On program's Front Panel:**  
3. Select `Gentec` port from drop-down menu (COM3 is default).
4. Select range of angles to be tested through. (For black materials, 10 to 180 degrees is default. For white materials, 10 to 90 degrees is default.)
5. Enter the name of material to be tested and select whether the trial will be for a material sample or for a reference sample. If material is being tested, select which reference sample data is being referenced. Reference samples save as two columns in .csv file (Angle and Power output), while material samples save as three (Angle, Reference Power output, Material Power output).  
    - *It is advised to run at least one Reference test for each day that data is collected.*  
6. For Lambertian testing, there is the extra option to "Home Laser". During this test, the laser arm does not move and thus, it is unnecessary to spend time bringing it to zero for every trial.  
    - *It is advised to home the laser before Reference data is collected.*  
7. The default "Data Sampling Info" as displayed should not need adjustments but the user has the freedom to do so if a test calls for it.  
8. Once material is securely clamped into the sample mount, the program can be run.  

## Warnings
- If the program is run till completion without a forced stop, the communication between LabVIEW and the LA's is still active. This allows for direct control to the LA's but it prevents other programs from controlling their motion. This means that before a Lambertian test can be run, the Specular test must be stopped, or vice versa.  
- Similarly, both LabVIEW and the APT User interface can not be simultaneously running or attempting to communicate with the LA's.  