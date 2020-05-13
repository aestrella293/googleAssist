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


## Begin Here! ##
***Step 1:*** Before loading the assistant to the Pi, note down the 'card number' and 'device number' of both your mic and speaker. These will be found using: 

- $ arecord -l

and

- $ aplay -l

*note:* the aux port (3.5mm jack) will usually be labelled as 'Analog'. 

***Step 2:***
