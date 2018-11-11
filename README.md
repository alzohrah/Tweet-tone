# Tweet-tone - analyze tweet sentiment in Node-RED

![`Tweet-tone`](images/1.jpg)

## Overview
Tweet's tone is an application to analyze each tweet sentiment, that has either specific hashtag or twitter user ID, in a real-time. IBM Tone Analyzer service has the ability to analyze the tweet's text that detects Anger, Fear, Joy, Sadness, and Disgust emotion tones which are most commonly used. Inside emotion tones, score of each tone based on the tweet's text. This service is one of other amazing IBM services which can be linked to the Twitter using a Node-RED application. In this project I use Node-RED installed in Raspberry Pi to connect the top three tone emotions of tweet and run RGB light based on specific color for each tone emotion. However, as you see above, this project is showing the powerful of IBM services for the developer by connect Twitter, IBM Tone Analyzer, and RGB light inside the Node-RED. Furthermore, these tone emotions remind me one of my favorite Disney movie called "Inside Out" which descripted all of five tone emotions inside the human, so I add the movie's characters picture in the UI to describe the tweet's tone emotion. 
In this tutorial, I walk you through the steps to create a Node-RED flow on Raspberry Pi and connect Twitter API to feed the tweet to IBM Tone Analyzer and then show the result on UI and RGB light - in under 60 minutes so let's start.

## Learning objectives

After completing this project, you will understand how to:
- [Install Node-RED on Raspberry Pi](#Install-Node-RED-on-Raspberry-Pi)
- [Create a Node-RED flow](#Create-a-Node-RED-flow)
- [Get Twitter API](#Get-Twitter-API)
- [Install IBM Watson nodes and UI Dashboard nodes](#Install-IBM-Watson-nodes-and-UI-Dashboard-nodes)
- [Install neopixel node for WS211 lights](#Install-neopixel-node-for-WS211-lights)
- [Connecting Tone Analyzer and Language Translator services](#Connecting-IBM-services)

## Prerequisites
In order to complete this project, you will need the following prerequisites:
- [IBM Cloud](https://www.ibm.com/cloud/) account - sign up if you don't have an account yet.

o	A Node-RED installed on Raspberry Pi 
o	IBM Tone Analyzer service
o	Twitter API
o	- [Language Translator](https://github.com/watson-developer-cloud/node-red-labs/blob/master/basic_examples/language_translator/README.md) service (optional if your language not support in Tone Analyzer)

o	ws8211 light (optional)

## Estimated time

- Creating a IBM services should take less than 10 minutes.
- Configuring ws8211 light should take less than 10 minutes.
- Developing the complete application on Node-RED should take less than 20 minutes.
- Completing the entire project should take approximately 25 minutes.

## Building the Tweet's Tone
### Install Node-RED on Raspberry Pi

Check if your Raspberry Pi has the latest Node-RED version installed or if you don't have click here. This tutorial is running on 0.19.2 Node-RED version.

### Create a Node-RED flow

Copy the code form the Tweet-tone flow file and import them into Node-RED clipboard:


- [Tweet-tone](tweet-tone.json)

![`Translator`](images/2.jpg)

### Get Twitter API
![`Translator`](images/3.jpg)


Frist of all, you have to get Twitter API to make this application works, so to do that visit this page [Twitter API](https://apps.twitter.com/) or double click on Twitter node then click on edit button and follow the instruction.  

![`Translator`](images/4.jpg)

### Install IBM Watson nodes and UI Dashboard nodes

In the Node-RED editor, you need to add IBM Watson nodes and UI Dashboard nodes. To do this:
1.	Select Manage palette from the upper right menu.

![`Translator`](images/5.jpg)

2.	From the Manage palette menu, click the Install tab then search for node-red-node-watson then install it.

![`Translator`](images/6.jpg)

3.	Research for node-red-dashboard then install it and close the palette menu.

![`Translator`](images/7.jpg)



### Install neopixel node for WS211 lights 

#### Pre-requisites
The Neopixel python driver need to be pre-installed... The easiest way to get the driver installed is to use the Unicorn HAT drivers install script. Before installing Unicorn Hat, it's good practice to update the software on your Pi. If you already know how to do this, go right ahead, otherwise you can read our [guide to "Keeping your Pi Up-to-date"](https://learn.pimoroni.com/tutorial/raspberry-pi/keeping-your-raspberry-pi-updated).

Unicorn Hat is easy to set up. We've created a one-liner ( that's one line of text you enter at the Terminal ) to get everything installed.

Open the Terminal and enter the following command:

curl -sS get.pimoroni.com/unicornhat | bash

After that, Install neopixel by running the following command in your Node-RED user directory - typically ~/.node-red and enter this commend;

npm install node-red-node-pi-neopixel

The data pin of the pixels should be connected to physical pin 12 - GPIO 18 of the Pi. 
Note: this may conflict with audio playback.




### Connecting IBM services


Now neopixel and Twitter node are connected and ready to use, let's start to 
Configure all of IBM services nodes: Tone Analyzer and Language Translator (optional)
1.	Go to your IBM services in IBM Cloud and copy the Service credentials

![`Translator`](images/8.jpg)

2.	Past the Service credentials inside the node as the following figure then click done.

![`Translator`](images/9.jpg)

### Deploy

After setup and configure everything, click on Deploy and test the application. Go to UI to see the dashboard by go to; {your IP or localhost}:{port}/ui

![`Translator`](images/10.jpg)


## Summary
Node-RED can make things easier. In this project, you have created a translator with a Telegram interface. This is sample and basic, and it can be modified and enhanced in respect to your needs.
