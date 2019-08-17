---
layout: single
title: MADLaSR
sidebar:
  nav: "side"
---
### Larry Gardner  
We have designed and built a device capable of measuring both the specular reflectivity of black materials, as well as the Lambertian reflectivity of white materials over their full range of incident and observed angles, respectively. The MADLaSR (Multi-Angle Detection of Lambertian and Specular Reflectivity) is a device designed for specular reflectivity testing in the range of 10° < θ < 170° and for Lambertian reflectivity testing in the range of 10° < θ < 85°. Here, we will describe the design and functionality of the MADLaSR.  

## Design  
This device consists of two distinct assemblies: the system of rotating arms and the sample mount, as shown in Figure 1.  

<figure>
  <img src="../assets/madlasr1.jpg" alt="Figure 1">
  <figcaption>Figure 1: MADLaSR Setup in the Munnerlyn Astronomical Instrumentation Laboratory in Texas A&M University</figcaption>
</figure>

The arms system is composed of a pivot rod with two t-slotted aluminum bars branching off. One arm holds a laser and the other holds a sensor; both of these are aligned to face in towards the pivot rod. The bars are mounted above two linear actuators and travel stages. Dowel pins are fitted into the travel stages and the grooves of the t-slot bars. The dowel pins are positioned on the travel stages such that they will remain symmetrical with respect to the pivot point and central axis during the stages' full range of travel.

The sample mount is a machined square tube with a window in the front face in which the material is exposed and secured by a swivel-leveling mount. This mount is supported by both a tilt stage and a translation stage in order to accommodate fine adjustments.

The two assemblies are then calibrated together such that the surface of the material sample (the reflection plane) is positioned perpendicular to the central axis and directly above the center of the pivot rod as shown in Figure 1.

Due to physical limitations, the minimum angle the MADLaSR can be positioned at is 10o. While it is capable of reaching a maximum spread of 180o, our results become potentially inaccurate at the largest angles. We choose to constrain our range of motion between 10° < θ < 170° for specular testing and 10° < θ < 85° for Lambertian testing.

## Specular Reflectivity Testing  
When testing for specular reflectivity, the laser and the sensor are moved to different positions symmetrically with respect to the central axis as defined by their pivot rod. An example of this setup is shown in Figure 2. By positioning iris diaphragms in front of both the laser and sensor, the diffuse scattering of the laser beam is minimized to ensure that we are measuring solely the specular reflection.  

<figure>
  <img src="../assets/madlasr2.jpg" alt="Figure 2">
  <figcaption>Figure 2: MADLaSR's Specular Reflectivity Testing</figcaption>
</figure>

## Lambertian Reflectivity Testing  
When testing for Lambertian reflectivity, the laser must be positioned perpendicular to the surface of the material while the sensor is moved to different angles. This setup, as shown in Figure 3, is designed to test for constant apparent surface brightness regardless of the angle of observation.  

<figure>
  <img src="../assets/madlasr3.jpg" alt="Figure 3">
  <figcaption>Figure 3: MADLaSR Running Lambertian Reflectivity Testing</figcaption>
</figure>

## Data Collection  
User interfaces, as shown in Figure 4, were made for both specular and Lambertian testing to allow for full customization of settings and the display of results in real time.  

<figure>
  <img src="../assets/madlasr4.jpg" alt="Figure 4">
  <figcaption>Figure 4: Specular Reflectivity User Interface</figcaption>
</figure>

The data collected consists of two key components: the angle between the laser and the sensor, and the corresponding power output. As the travel stage moves, the position is recorded and converted into the current angle. This value is used to determine the following angle to take data at and thus, can calculate the next position to move to. Data is taken at intervals of 2 degrees.  
Once the travel stages move to their positions, they wait while the Gentec sensor collects data. This sensor records 25 data points and averages them together at each angle interval. While the arms are moving to new positions, the average is reset and prepares for the next sampling period.  

## Procedure

1. Secure Ocean Optics reference sample into the mount.  
2. Run initial test using the "Reference" settings as shown on the user interface.  
3. When finished, replace the reference sample with a material sample.  
4. Select the "Test Sample" toggle switch on the user interface.  
5. Select the file path produced by step (2) to establish the reference data for the test sample data file.  
6. Run test on material sample.  
7. Repeat steps (4) to (6) with new material sample.  

For more complete instructions, please read the <a href="../madlasr_usermanual/">User Manual</a>.  


## Specular Reflectance Measurements  
In order to measure the specular reflectance for our samples, we used a Helium-Neon laser to reflect off the surface of each of our samples at 10°, 22°, and 44° and used a Gentec Photo-Detector to measure the specular intensity at a specific distance away from the sample.  
<br>
**Experimental Setup:**  
Below is the setup we constructed on an optics bench in the Munnerlyn Astronomical Instrumentation Laboratory at Texas A&M University. Our setup, shown below, consists of a mounted Helium-Neon laser (top-left) which is reflected off the angled sample (top-right) and sent towards the photodiode detector (middle-left) where an intensity measurement is taken using the Gentec photo-detector (bottom-middle). All measurements were taken in a dark room environment.
<figure style='max-width: 60%'>
  <img src="../assets/specularsetup.jpg" alt="Specular setup">
</figure>
**Procedure:**  
1. Align the laser using a mirror to make sure it is incident on the center of both the angled sample and the photodiode.  
2. Take a measurement of the initial intensity of the laser. This can fluctuate over a few hundredths of milliwatts.  
3. Take measurements of all the samples at the desired angle while being careful not to bump any components.  
4. Using a mirror, check again that the laser still is centered on the photodiode after the measurement.  
5. Change the angle of the sample if desired and continue taking measurements by repeating these steps.  
**Data Analysis:**  
1. The specular reflectance value is calculated by taking the detected power of the sample and dividing by the initial intensity of the laser.
2. With the specular reflectance value coupled with the total reflectance values (MCF) we calculated the diffuse reflectance values.
3. Finally, we took the ratios of the specular and diffuse components to analyze each sample's fraction of specular reflectance (shown below).

Gentec Photodiode: PH100-SiUV (S/N: 181951, <a href="../assets/PH_2012_V1.0.pdf">datasheet link</a>)

## List and Measurements of Sample Materials
Please <a href="../samples/">click here</a> for a detailed list of sample materials and their associated <a href="../reflectance_plots/">plots</a>.
