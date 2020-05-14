# EL2020 Final Project
## Google Assistant ##

Professor: Joshua Simons

Student: Alexander Estrella

This repository contains all the code and instructions necessary to set up a Raspberry Pi to function as a Google Assistant.

**Functionality**
- Audio input through a microphone
- Playback of the assistant response 
- Volume control
- GPIO control

**Prerequisites**
- Raspberry Pi 3 or 4 with the latest update to the raspbian/python software.
- A USB microphone
- Speaker with an aux port (or bluetooth but for my purposes I used the aux port on the pi)
- A Google account to link the project

## Getting approval from Google ##
***Step 1:*** From https://console.actions.google.com/ create a new Project. For this project I used 'el2020ga'.

***Step 2:*** A Google project can come inn many forms (games, apps, smart home,...) we will choose *'Device Resigstration'* to register our Raspberry Pi with Google. 

Select *'register model'* on the next page. 

The device type should be a *'Speaker'*.

**Make sure you download the 'Oauth 2.0 credentials' to your Pi. You may download them to your PC but they must be moved to the Pi later.** 

For this project the only trait selected was the *'On/Off'* trait.

***Step 3:*** Next, go to https://console.developers.google.com/apis

## Setup of the Pi ##
***Step 1:*** Before loading the assistant to the Pi, note down the 'card number' and 'device number' of both your mic and speaker. These will be found using: 

- $ arecord -l

and

- $ aplay -l

*note:* the aux port (3.5mm jack) will usually be labelled as 'Analog'. 

***Step 2:*** Make a file named ".asoundrc" 
