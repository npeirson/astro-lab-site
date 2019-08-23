---
layout: single
title: PreCal Documentation
sidebar:
  nav: "side"
toc: true
rtt: true
---
<b>Nicholas Mondrik</b> 

## Introduction  
PreCal is a monochromator based system that can scan the throughput of any system capable of being attached to an SBIG camera. Current testing has been done only on the lab's ST-8300M (red) SBIG camera, but since SBIG uses a universal driver system, any SBIG camera should be compatible with the system. (I stress SHOULD, I cannot guarantee that it will work, but since the function calls for the SBIG driver go through their universal driver, they should work for all SBIG cameras). 

## Installation  
The PreCal system exists entirely on the monochromator cart, and is currently installed only on the black laptop named Nymeria. To install the PreCal software on another computer, download the MoCoAuto.zip file at the end of this page and follow the instructions in the README.txt file. I have included pictures of the things that need to be changed in LabVIEW to help clarify any confusion. The first thing you should do when you want to install the system on a new laptop is to go to [this link](https://www.sbig.com/support/software/) and download DriverChecker64. This will install (some of) the drivers needed for the camera to run properly. This figure indicates what should be changed in order for the LabVIEW program to correctly locate and run the CCDAutomation.exe file. The upper most path constant should be the path to the directory where the `MOCOAUTOMATION_1.0.vi` is located, with the filename `CCDrunfile.bat` appended. This is how the program creates the .bat file that is used to launch the CCD control software. The lower left box (the string constant) indicates the path to the `CCDAutomation.exe` file, with a cd in front. Thus, it should read `cd [your_path_here]\CCDAutomation.exe`. This tells the command prompt to change to the correct directory and run the .exe file. The second (lower right) path constant specifies the working directory. In reality, this should be the same directory where the .vi file is located, but I have included it to allow for more flexibility in future operations.  
<figure>
	<a href="/instruments/assets/precal_figure1.png" target="_blank"><img src="/instruments/assets/precal_figure1.png"></a>
	<figcaption>
		The red boxes indicate the major areas of concern: The correct cases, and the location of the variable to change within the cases.
	</figcaption>
</figure>
The next two figures show where the constants must be changed in the middle of the program, in the main case structure. Again, the box at the top specifies the correct case, and the other boxes (in this case, all path constants) should have the following value- `[your_path_here]\communication.txt`. These values should be the same for both the "Photodiode Acquire" and "Acquire Dark" cases.  
<figure>
	<a href="/instruments/assets/precal_figure2.png" target="_blank"><img src="/instruments/assets/precal_figure2.png"></a>
</figure>
<figure>
	<a href="/instruments/assets/precal_figure3.png" target="_blank"><img src="/instruments/assets/precal_figure3.png"></a>
</figure>

This next figure notes the location of the path constant to change for the shutdown file. Again, it should lead to the same directories as the above values, except have the `shutdown.txt` part appended, (ie, `[your_path_here]\shutdown.txt`).  
<figure>
	<a href="/instruments/assets/precal_figure4.png" target="_blank"><img src="/instruments/assets/precal_figure4.png"></a>
</figure>

## Operation  
The following is the procedure to begin a scan:

1. Plug in and power on photodiode, arc lamp, and monochromator controller.  
2. Start up `MOCOAUTOMATION_1.0.vi` and `1608fsdr_v2.vi` and change to the correct parameters. The monochromator should inherit its settings from its .ini file, but the photodiode program (the `1608fsdr_v2.vi`) needs to be set manually. The voltages should be +/- 5V, but the path and name of the save file have no name restrictions.  
3. To begin a scan, click the automation button on the front panel of the `MOCOAUTOMATION_1.0.vi` and fill in the desired parameters. A quick explanation on the temperature regulation: the up-down switch controls the temperature regulation of the camera (up for on, down for off). The light-up button enables a 5min wait immediately before the scan, so the camera can reach the desired temperature. If you are using the ST-8300M SBIG camera, it is highly recommended that you use temperature control, as the camera has extremely high read noise and dark current.  
4. After you are finished entering scan parameters, click the OK button, and the monochromator should move to the starting wavelength and begin its cycles.  
5. After the scan is done, it is best to use the STOP button in the lower right of the front panel to shut off the program, as this allows the drivers to exit properly.  
  
USE THE STOP BUTTON ON THE FRONT PANEL FOR THE PHOTODIODE PROGRAM. IF YOU DO NOT, THE MASTER FILE WILL NOT BE GENERATED AND YOU WILL HAVE TO WRITE A SCRIPT TO REDUCE ALL OF THE DATA FROM THE INDIVIDUAL FILES YOURSELF.  
  
If you exit a scan early:  
- You will have to stop the `CCDAutomation.exe` manually. You can do this by going to its command prompt window and pressing `Ctrl+C`. Then enter `Y` to indicate that you want to cancel all jobs.  
- Next you will have to navigate to the directory where you set the `communication.txt` file and delete the `communication.txt` file if it is present. Depending on when exactly you canceled, the process, it may or may not be present.  
- In addition, if the shutter was open when you stopped the `MOCOAUTOMATION_1.0.vi`, you will need to close it before starting another scan. You can do this by just starting the program, then changing to the operation tab, and hitting the close button.  
- You will also need to stop the `1608fsdr_v2.vi` program and delete all of the photodiode files to ensure consistent data. The photodiode program appends data, rather than overwriting the file, so this step is crucial. 

## A Few Notes on How the Program Operates
PreCal consists of 3 main parts: the LabVIEW driver for the system (`MOCOAUTOMATION_1.0.vi`), the photodiode software (`1608fsdr_v2.vi`) and the software to control the CCD (`CCDAutomation.exe`). The first two pieces of software can be used for other purposes, but the latter is reserved for PreCal use only. The way the PreCal system operates is as follows:  
1. A request for a scan is submitted by the user. The user inputs all scan parameters.  
2. A `CCDrunfile.bat` file is created by the LabVIEW driver. This batch file is used to start the `CCDAutomation.exe` file, and pass command line arguments to the program. This is how scan parameters are passed to the CCD controller software.  
3. The CCD software initializes a link to the camera, and will output its current status to the command line. During this stage, the LabVIEW driver is told to wait for a short while so that the link may be established.  
4. The LabVIEW driver then moves the monochromator to the starting wavelength. When the wavelength is reached, it pauses for a second to allow the photodiode time to respond, then creates a file called `communication.txt` in the specified directory, then turns on photodiode saving (photodiode saving is on a timer for the exposure time length). This file tells the CCD software to take an exposure. The CCD software was passed the scan parameters, and thus keeps track of the current wavelength internally, rather than being passed information by the LabVIEW program.  
5. The first time a communication is passed is during a "Photodiode Acquire" case action in the LabVIEW program (the name is a carryover from previous work). This communication file is then detected by the CCD control program, and the program takes an exposure and names it accordingly. It then changes it internal state to a dark state. The CCD controller then deletes the `communication.txt` file, and returns to its idle state.  
6. The LabVIEW program detects the deletion of the `communication.txt` file, and move to the next case, which is now "Acquire Dark" (actually, it closes the shutter, then goes to the "Acquire Dark" case). After closing the shutter, it again creates a `communication.txt` file, and the CCD program takes over, while the photodiode again begins saving (on a timer, of course).  
7. Since the CCD switched its internal case to dark last time, it now 'knows' that this is a dark exposure. It therefore takes an exposure exactly as last time, but appends "dark" to the output files. After the exposure it sets its internal case to 'light', deletes the `communication.txt` file, and is ready for the next light exposure.  
8. After the LabVIEW detect the deletion of the `communication.txt` file, it moves to the next wavelength, and the process from step 5.  

## Why Didn't You Do It This Way??
Q: Why is the photodiode on a timer? Wouldn't it be better if the CCD program told the LabVIEW program exctly when the exposure was finished, so the data is as accurate as possible?  
A:Yes, it would be better. In fact, when I first began developing this method, I had exactly that. However, I ran into problems with the CCD going from "Exposing....Exposing...Exposing...->Idle" with no readout state in between. After much pulling of hair and gnashing of teeth, it was eventually determined that the problem was with the `GetGrabState()` function used in the CCD control software. For some reason, when this step was removed, (it was threaded, in order to allow for monitoring, as the `GrabImage()` function blocks the main program), the CCD had no problems. It was therefore decided that a timer was Good Enough™.  

Q: Why is PreCal split into three separate programs? Wouldn't it be easier if these were all one program in one language?  

A: This has a few reasons- One: part (much) of the work for the LabVIEW portion was already complete, so I wasn't going to redo work that was already finished. Two: the SBIG program (and drivers!) that I hacked apart and rebuilt to control the camera were written in C++, and importing the C++ libraries into LabVIEW was a no-go for reasons I won't go into here. However, there does exist a thing called ASCOM, which allows control of basic functions for a variety of equipment from a centralized driver through ASCOM. Fortunately, the LabVIEW language is supported by ASCOM. Unfortunately, SBIG does not have ASCOM drivers for their cameras. If we had an ASCOM compliant CCD, we could implement the entire process in LabVIEW. You can read more about ASCOM [here.](http://ascom-standards.org/)  

## Data Reduction  
I have included with the control software a small script called `reductionscript.py` in the conveniently named `Python_Analysis_Script` directory. The purpose of this script is go through the master photodiode file and alert you to any wavelengths where the photodiode may have saturated, and to output a text file with the following structure:  
<small>[WAVELENGTH | AVG PD LIGHT VAL | AVG PD DARK VAL | ADJ AVG VAL | PHOTONS/SEC]</small>  
With the values listed under the columns. This program assumes you are using one of the calibrated photodiodes we have, so if you have a different one, you cannot use this program. In addition, the calibration is only valid between 300nm-900nm, so you cannot use this program outside of this range. It is possible to extrapolate calibration values from the curve, but I cannot guarantee that they will be valid, so you're on your own if you want to do that. (Also, you should probably read the README.txt file for more information on this process. In addition, since it's python code, you can also just look at the script to get an idea of whats going on behind the scenes).  

## A Quick IRAF Introduction  
I won't go through the grueling task that is installing IRAF. Instead, I will forget all those horrid memories and imagine a world in which IRAF is already installed on whatever computer you're using. (Actually, its not that bad. You can go to [this site](http://www.astrosen.unam.mx/~favilac/IRAF/) to get an .iso file for your appropriate Linux distro, then follow [these instruction](https://instrumentation.tamu.edu/files/precaldocumentation/irafinstructions.txt) to install it).  
Now that IRAF is fired up and running, you can do the following:  
Within IRAF, navigate to the directory with all the .fits files.  
`(cl> cd /your/directory/here/).`  
Use the files command, and pipe the output to a file for later access. It should look something like this:  
```
cl> files *nm.fits > LightList.txt  
cl> files *dark.fits > DarkList.txt  
```
You can open these files to verify that they contain the light and dark fits files, respectively. Now that we have the lists, we can do some image arithmatic with the imarith command by doing  

`cl> imarith @LightList.txt - @DarkList.txt @LightList.txt`  

This subtracts the darks from all of the lights, and stores the resulting image in the light image  
`!!THIS WILL OVERWRITE THE LIGHT IMAGE!! !!MAKE SURE YOU HAVE BACKUPS!!`  
You don't have to rewrite the light image, but based on the size of the fits files and length of the scan, this will use a good chunk of memory, so this helps minimize the amount used.  
Next, we can use the imstat command to list statistics about the images by typing  
`cl> imstat @LightList.txt > StatList.txt`  
Again, this takes the output of imstat and pipes it to the StatList.txt file, which you can then access with your favorite scripting/plotting language.  
If you want to learn more about IRAF, you can find an excellent tutorial by Josh Walawender here.  
Now that we have IRAF out of the way, we can move on to the final step: combining the photodiode data with the image data.
Since everyone uses their own language to do data reduction, I'll describe the process here, but leave implementation up to you.  
1. Import the image (from the `StatList.txt` file generated earlier) and photodiode data (from either the Python script, or from your own work).  
2. Divide the mean counts in each image at each wavelength by the photons/sec value obtained from the photodiode data. This scales the values at each wavelength to the amount of light put out by the lamp at each wavelength. Imagine a scenario where you have an average count value of 500 at 500nm, and an average count value of 500 at 800nm. If your lamp puts out 2x the light at 800nm than it does at 500nm, the your lamp is ½ as efficient at 800nm than it is at 500nm. Thus, dividing by the light output (as measured by the photodiode) decouples the spectrum of the lamp from the throughput curve.  
3. Now, we have the correct shape, but a bunch of crazy values. To make the values reasonable, normalize all of the values by the maximum value in the graph. That is, `y_new[i] = y_old[i] / y_max[all i]`  
4. Ta-da! All done! Plot throughput and wavelength in the grapher of your choice and you're all done!  
To check yourself, here are some throughput plot I have made (using a manual, rather than automated system for the first two, and PreCal for the last). Note that there are 3 lenses and two CCDs in these graphs. The first two used 500mm and 300mm lenses that we had in the lab for another project, as well as an Apogee CCD, and the third image (the one that used PreCal) used a small Nikon lens that connects directly to the SBIG ST-8300M CCD.  

<small>Note: This first plot has a point where I accidentally let the photodiode saturate. This is what it looks like if that accidentally makes it through to the plotting stage.</small>  

<figure>
	<img src="/instruments/assets/precal_figure5.png">
</figure>
<figure>
	<img src="/instruments/assets/precal_figure6.png">
</figure>

## Basic Troubleshooting  
- For errors with the CCD automation software:  
- Is the CCD plugged in and powered on?  
- Is the C++ redistributable installed correctly?  
- Have all of the paths been changed appropriately?  
- Is the `shutdown.txt` file deleted from the directory where the executable is located?  
- Is the `communication.txt` file deleted from the directory where the executable is located?  
- Is the `cfitsio.dll` in the same directory as the .exe file?  
- Check where the `communication.txt` file is being created. Is it in the same directory as `CCDautomation.exe`?  
- If you hit start from the automation prompt and the command prompt windows opens and immediately closes, check to see whether the CCD is plugged in. If it is, try unplugging it and waiting a few seconds, then plugging it back in.  

- For errors with the `MOCOAUTOMATION_1.0.vi`:  
  - Is the monochromator controller plugged in and powered on?  
- If you are using the Serial -> USB connector, make sure you have the appropriate driver installed. For the Dynex one, there is a driver in the drivers and libraries folder named `PL2303_Prolific_DriverInstaller_v1210.exe`. If you are using a different converter, make sure you have properly installed the appropriate driver.  
- If the software still does not recognize the controller, make sure the appropriate COM port (COM1) is being used. If you use a converter, the OS often will not assign the COM port as COM1, even if there are no other COM ports on the machine. To change this, go to  
`Control Panel >> Device Manager >> Ports >> [Your Converter here] >> Right Click >> Properties >> >> Port Settings >> Advanced >> Change Port Number to 1`  
- If you have just installed the software on a new computer, you may need a .ini file to tell the controller how it should configure itself. There is a copy of a good one in the `Drivers_and_Libraries` directory. This is the file that is saved whenever you click the save settings button.  
- For errors with the photodiode software:  
  - Did you correctly run instacal?  
  - Did you set the proper values on the front panel?  
  - Did you enter the correct file path to an *existing directory* in the save location box?  
- If all else fails, restart the computer and try again.

## Final Notes  
This system, process, and wiki page were put together during Summer 2013 by Nicholas Mondrik. If you have any questions, you can email me at nmondrik@gmail.com, and I will try to help you as much as I can. Unfortunately, I did not write all of the LabVIEW code, as parts of the LabVIEW code were shipped with the monochromator controller, so my help with the LabVIEW portion may be limited.  
[last updated 6/25/14 by N.M.]