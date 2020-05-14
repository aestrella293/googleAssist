# EL2020 Final Project
## Google Assistant ##

Professor: Joshua Simons

Student: Alexander Estrella

This repository contains all the code and instructions necessary to set up a Raspberry Pi to function as a Google Assistant through the Google API.

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

***Step 5:***   Use the tab bar to go to the *'OAuth Consent Screen'* and designate your project as *'External'* on the next screen.

On the next page, you only need to confirm the email being used with this project. Then click *'Save'.* 

## Setup of the Pi ##
A good check before setting up the rest of the Pi would be to `$ sudo apt-get update` and `$ sudo apt-get upgrade`.

***Step 1:*** Next is to note down the 'card number' and 'device number' of both your mic and speaker (if ti is plugged in by USB). These will be found using: `$ arecord -l` and `$ aplay -l`

_**note:** The aux port (3.5mm jack) may be labelled as 'Analog'._

***Step 2:*** Make a file named '.asoundrc' in your home directory with the following code:
```
pcm.!default {
  type asym
  capture.pcm "mic"
  playback.pcm "speaker"
}
pcm.mic {
  type plug
  slave {
    pcm "hw:[card number],[device number]"
  }
}
pcm.speaker {
  type plug
  slave {
    pcm "hw:[card number],[device number]"
  }
}
```
Replace the fields surrounded in brackets with the numbers found in the last step.
Save and exit.

***Step 3:*** Issue the command `$ sudo apt-get install python3-dev python3-venv` to download the virtual environment python code. 

After issue `$ python3-m venv env` to give the code access to issue commands to the virtual environment.

***Step 4:*** Next we want to give the environment the tools it needs to operate. Issue `$ env/bin/python -m pip install --upgrade pip setuptools wheel` to upgrade the 'setuptools' necessary.

***Step 5:***
__*From this point onward we will be working with the virtual environment that we just set up. In this environment we are treating the commands as if were a "Google Assistant" not just the Raspberry Pi.*__

Issue `$ source env/bin/activate` to enter the environment.

And `$ sudo apt-get install portaudio19-dev libffi-dev libssl-dev` to install  the libraries of the dependencies that the assistant will be looking for.

***Step 6:*** Now to install the project that was created through the Google console. Issue the command `$ python -m pip install --upgrade google-assistant-sdk[samples]`.

Now the Raspberry Pi has all its necessary code to function with the traits given earlier. However in order to 




























































