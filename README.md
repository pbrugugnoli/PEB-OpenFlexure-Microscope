# PEB-OpenFlexure-Microscope

## Overview
This microscope is an implementation of the [OpenFlexure Microscope](https://openflexure.org)  (v7-beta) adjusted to my specific needs:
- be able to analyze thick samples (no transparent ones)
- be able to analyze heavy samples (that cannot be hanged down)<br>
  
The main features of the OFM are:
- upright model of the ofm 
- custom board to connect Arduino Nano, stepper drivers (2PH124959A), led drivers (LDO6AJSA)
- 3W led for the epi-illumination + 1W led for the trans-illumination
- magnetic connection to exchange between epi and trans illumination (with and without beamsplitter)
- beamsplitter cube and cube holder to hang the cube upside-down (upright ofm)
- RaspberryPI 2B and PICamera V1.3 - affordable and available components in Brazil
- 40x Objective with a achromatic 50mm lens

## Build
  <table border="0">
   <tr>
      <td><b style="font-size:30px">Printing picture</b></td>
      <td><b style="font-size:30px">Printed Parts</b></td>
      <td><b style="font-size:30px">First Assembly with temporary feet</b></td>
   </tr>
   <tr>
      <td><img src="https://github.com/pbrugugnoli/PEB-OpenFlexure-Microscope/blob/main/images/OFM%20-%20printing.jpg" width="300"/></td>
      <td><img src="https://github.com/pbrugugnoli/PEB-OpenFlexure-Microscope/blob/main/images/OFM%20-%20printed.jpg" width="300"/></td>
      <td><img src="https://github.com/pbrugugnoli/PEB-OpenFlexure-Microscope/blob/main/images/OFM%20-%20assembly%20with%20temporary%20feet.jpg" width="300"/></td>
   </tr>
  </table>

## Optics and illumination
There are a lot of pending improvement, still to be performed, regarding the optics and illumination systems:
1. Add led drivers (LDO6AJSA) to control led power by software using PWM signal;
2. Objective alignment - due to the weight of the objective in the upright microscope model, the object tends to tilt;
3. There should be a gross and fine adjustment of the distance from the sample to the objective - the motor of the current version only allow the fine adjustment (automatic focus);
4. The assembly (fixation mechanis) of the PiCamera V1.3 should should allow some x-y fine tune position adjustment;
5. Change the 1W with LED for a RGB LED to allow experiment with different color ilumination (UV-light) and also fine lens shading calibration.<br>

Some pictures about the current implementation:
  <table border="0">
   <tr>
      <td><b style="font-size:30px">Objective</b></td>
      <td><b style="font-size:30px">Trans-Illumination</b></td>
      <td><b style="font-size:30px">Epi-Illumination</b></td>
   </tr>
   <tr>
      <td><img src="https://github.com/pbrugugnoli/PEB-OpenFlexure-Microscope/blob/main/images/OFM%20-%20objective%20and%20sample%20zoom.jpg" width="300"/></td>
      <td><img src="https://github.com/pbrugugnoli/PEB-OpenFlexure-Microscope/blob/main/images/OFM%20-%20epi%20and%20trans%20illumination%20alternatives%201.jpg" width="300"/></td>
      <td><img src="https://github.com/pbrugugnoli/PEB-OpenFlexure-Microscope/blob/main/images/OFM%20-%20epi%20and%20trans%20illumination%20alternatives%202.jpg" width="300"/></td>
   </tr>
  </table>

## Electronics
A small board (perforated board) is used to connect the Arduino Nano to the stepper motor drivers and led drivers, whilst the firmware code was adjusted to support both used header pins and to provide the PWM signal for light intensity control
  <table border="0">
   <tr>
      <td><b style="font-size:30px">Board Schematics</b></td>
      <td><b style="font-size:30px">Implementation</b></td>
   </tr>
   <tr>
      <td><img src="https://github.com/pbrugugnoli/PEB-OpenFlexure-Microscope/blob/main/images/OFM%20-%20Custom%20board.png" width="300"/></td>
      <td><img src="https://github.com/pbrugugnoli/PEB-OpenFlexure-Microscope/blob/main/images/OFM%20-%20Electronics.jpg" width="300"/></td>
   </tr>
  </table>

## Software
- Both the automatic white balancing (AWB) and the lens shading correction (LSC) was incorrect for PiCamera V1.3
- After some reverse engineering,  2 pull requests were created to address and appropriated manage AWB and LSC for the Picamera V1.3 in PiCameraX and OFM Server programs
- [My contribution to the community](https://openflexure.discourse.group/t/rpi-1b-picamera-v1-3-auto-calibration-solved/1486/6)

## Demo Video - OFM at work 
- [![Demo](https://github.com/pbrugugnoli/PEB-OpenFlexure-Microscope/blob/main/images/OFM%20-%20upright%20objective.jpg)](https://youtu.be/tEzmvFiI1ls)

