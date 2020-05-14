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
This process can be performed on the Raspberry Pi itself or on a seperate PC. The credentials would have to be moved onto the Pi itself later before continuing.

***Step 1:*** Before anything, go to https://myaccount.google.com/activitycontrols.

Make sure the following controls are enabled:
- Web & App activity
- Location History
- Device Information
- Voices & Audio Activity

This will allow the assistant to perform its basic functions. 

***Step 2:*** From https://console.actions.google.com/ create a new Project. For this project I used 'el2020ga'.

***Step 3:*** A Google project can come inn many forms (games, apps, smart home,...) we will choose *'Device Resigstration'* to register our Raspberry Pi with Google. 

Select *'Register Model'* on the next page. 

The device type should be a *'Speaker'*.

**Make sure you download the 'Oauth 2.0 credentials' to your Pi. You may download them to your PC but they must be moved to the Pi later.** 

For this project, select the *'On/Off'* trait.

***Step 4:*** Next, go to https://console.developers.google.com/apis and select *'Enable Apps and Services'.*

Search for and enable the Google Assistant API.

***Step 5:*** Use the tab bar to go to the *'OAuth Consent Screen'* and designate your project as *'External'* on the next screen.

On the next page, you only need to confirm the email being used with this project. Then click *'Save'.* 

## Setup of the Pi ##
***Step 1:*** Before loading the assistant to the Pi, note down the 'card number' and 'device number' of both your mic and speaker. These will be found using: 

'$ arecord -l' and '$ aplay -l'

*note:* the aux port (3.5mm jack) will usually be labelled as 'Analog'. 

***Step 2:*** Make a file named ".asoundrc" 
