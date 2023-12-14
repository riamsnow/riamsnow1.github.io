---
title: "DaLock by SmartHub"
excerpt: "A biometric smart lock to simplify dorm room access."
header:
  teaser: assets/img/dalock-teaser.jpeg
# gallery:
#   - image_path: assets/img/lithub1.jpeg
#   - image_path: assets/img/lithub2.jpeg
#   - image_path: assets/img/lithub3.jpeg
   
---

# Motivation
As an RA at Vanderbilt, I've had my fair share of residents lose their room keys. If you didn't know, a lost key incurs a fine of $50 and a long wait for your room to be rekeyed. I recently acquired an Adafruit Fingerprint sensor and knew what had to be done.

DaLock (by SmartHub) changes the game! I wanted to mitigate the risk of paying $50, while building something cool.

# Design
As with most microcontroller projects, you start out big and slowly find ways to shrink the form factor of your product. This project started with an Arduino Uno, fingerprint sensor, stepper motor, and a dream. I wanted to build something sleek and compact, without sacrificing functionality. DaLock v1 is my first attempt at making this happen. Below are some design features I'm particularly fond of:

  * All electrical components are neatly hidden away in a 3D printed enclosure.
  * The data and power ports of the Arduino are easily accessible to allow for user modifications. 
  * The entire device is powered by a 9v battery, which is easily accessible on the outside of the enclosure.
  * Timeout feature automatically locks the door after 10 minutes have elapsed.

# Cost
See the sourced materials and their associated costs below. For ~$80 (and access to a 3D printer), I was able to develop a product with the same core funcionality as competitors. 

|                 Component                 | Image | Cost |
|:-----------------------------------------:|:-----:|:------: |
|      Adafruit Fingerprint Sensor          |   ![](/assets/img/adafruit-fingerprint-sensor.jpeg)           |$39.95|
|      Arduino Uno                          |   ![](/assets/img/arduino-uno.jpeg)                           |$27.60|
|      Stepper Motor & Driver               |   ![](/assets/img/stepper.jpg)                                |$7.99|
|      Battery Connector                    |   ![](/assets/img/battery-jack.jpg)                           |$5.99|
|      Assorted Jumper Wires                |   ![](/assets/img/jumper-wires.jpg)                           |$6.99|

<iframe width="560" height="315" src="https://www.youtube.com/embed/8njMQH4eVs8?si=7cWinN3lqpxoW8n6" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


<!-- {% include gallery %} -->
