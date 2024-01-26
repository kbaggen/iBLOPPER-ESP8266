# iBLOPPER-ESP8266

## What is the iBLOPPER?
iBLOPPER is a Bubble Logger or more precise an activity fermentation logger and temperature controller to be attached to your (S)airlock. It detects the release of a bubble, reporting, Blops pr. min (BPM), indicative SG estimate and temperature into iBLOPPER CLOUD.

We support two different versions of iBLOPPER either detection by vibration/gyroscope sensor (iBLOPPERV) or by using a sound sensor (iBLOPPERS). By 2023 we promote the sound version as best suited for (s)airlocks and most users. A

Secondly, the iBLOPPER can trigger a set of Wifi Smart Plug from Shelly or Tasmota over your local internet by http commands and hence you can control your frezzer/heating agent from iBLOPPER CLOUD.

To use the “iBLOPPER” just attach the iBLOPPER to your airlock, then enter your brew details at iBLOPPER CLOUD. During the brew at preferably after high kreutzen you will need to take one hydrometer reading and by very simple math you will be able to predict the final gravity by a few units. All while you monitor from the outside of the fermenter.

![image](https://github.com/kbaggen/iBLOPPER-ESP8266/assets/16992918/2af5d56a-ccba-4deb-912c-fb24895f3323)


## iBLOPPER CLOUD CONNECTED. 
The Logger is completely autonomous, hence, only need wifi credentials set once and else all handling/controlling is entirely done at the iBLOPPER CLOUD page. Hence, please register with your 7-8 cipher unique iBLOPPER Number at iBLOPPER CLOUD.

At the CLOUD you can set brew name, size, OG and polynomial for speed of fermentation. You can ofcouse start, stop and delete logged brews.

You can change setting for Fahrenheit, set time zone and forward the current Active Brew till BrewSpy, Brewfather, Ubidots or Brewersfriend if you wish. A RESTfull API is also provided for attaching data till other services.

iBLOPPER CLOUD is a crude installment for a CLOUD service, but continuedly work is planned.
![image](https://github.com/kbaggen/iBLOPPER-ESP8266/assets/16992918/c4cd66f5-4747-48d3-bb0e-28912a91ebf6)



## Temperatur Control by Smart Wifi Plug
iBLOPPER (from version 4.0.0 of early 2023) can trigger a set of Wifi Smart Plug from Shelly or Tasmota over your local internet by http commands and hence you can control your frezzer/heating agent from iBLOPPER CLOUD.

Currently we propose you buy “Athom – Tasmota Plug” as they is avaivble, very easy to set up and shiped all over the globe.

All plugs need to be on same local network as the iBLOPPER and hence, the iBLOPPER will trigger the plug by http command over the local network. 
![image](https://github.com/kbaggen/iBLOPPER-ESP8266/assets/16992918/e890aaf4-c982-443d-82de-7b36696d4c46)


## Further interduction
The iBLOPPER is an Arduino device (ESP8266). It monitor your yeast activity by motioning the CO2 blops pr. minute (BPM). Besides BPM, also “Sum blops/L” and temperature is logged. Based on Sum Blops/L indicative gravity estimate is given by polynomial/modelistic approach.

We support two different versions of iBLOPPER either detection by vibration/gyroscope sensor (iBLOPPERV) or by using a sound sensor (iBLOPPERS).


It works by placing iBLOPPER on the outside of the airlock, and iBLOPPER then detects the tiny movement or sound the airlock makes at the release of a bubble. Hence, it need placed away from vibrations and/or high sound sources dependent on the version you are using. For especially the vibration model; use flamingo mat in cooler or similarly + and ensure the fermenter and iBLOPPER cables is isolated from vibrations.


The software can though the “Sum Blops/L” be used to give an indicative SG/rG (reduction in gravity) by polynomial approach. To ensure a reliable SG estimation and to account for the many factors affecting CO2 release the users needs to conduct a midterm “one hydrometer reading” when preferably high kreuzen has just passed and hence re-calculating and updating the polynomial for the current brew by simple maths.

All data is then send easily till iBLOPPER CLOUD.

How to:

* Attach iBLOPPER till your S-airlock.
* Use a S-airlock. Use 5ml water in it.
* Goto iBLOPPER CLOUD and enter Brewname, OG, Brewsize.
* Decide on Start-out polynomial at iBLOPPER CLOUD.
* Follow the Blop pr. min (BPM) at iBLOPPER CLOUD.
* During 50-75% into fermentation (preferably when high kreuzen has passed), take one midterm hydrometer reading. Calculate the speed of fermentation (polynomial) by the provided tool at iBLOPPER CLOUD.

That its. Hence, this way you can foresee the final SG by an error of mean of 3 points.
Hydrometer reading of OG and “one hydrometer reading” must be precise. This give you full insight in the fermentation, by activity, temperature, and how far it have come through indicative SG estimate. All by not adding anything into the wort.

(1 Reduction in gravity, rG = OG – SG)

## Videos
https://youtu.be/rfGtCtaYLWA
https://youtu.be/XYqAmXFoWy8


# How To build, install and setup?
## Sound Version
To build the sound version you will need a:

1x NodeMCU V2

1x LM393 sound sensor

1x 70cm 3 pin cord (female till female).

1x DFrobort temperature sensor (d18b20)

1x Waterproof-Plastic-Electric-Project-Case-Junction-Box-55x35x15mm or or just a TickTax box.
![image](https://github.com/kbaggen/iBLOPPER-ESP8266/assets/16992918/2696ecd9-ce55-4228-b4ec-eb42b9eb467c)


Pinout:

The sound sensor is connected so VCC goes till D0, and GRD till D1, while out (data) goes till D2.

For temperature probe you connect GRD till D5, and VCC till D6, while data goes till D7.
![image](https://github.com/kbaggen/iBLOPPER-ESP8266/assets/16992918/7082cfe7-6afc-4fe4-95d9-b053fdbb2b58)


Building Sound Sensor?

Building the sound sensor.
Building the sound sensor is easy, and you just need to add a bit of tape to steady the microphone. Secondly, add a balloon as moisture protection.

The LM393 sensor fits nicely in a S-airlock, and should be pressed whole way down. It should still allowe the pressure to get out, but else make a somehow tight “seal”.

The sensitivity of the sound sensor can be adjusted by the small potentiometer on the sensor. In general turn the potentiometer all the way down till LED light fully, and then just turn it down until light stop + a little nudge more.

In iBLOPPER CLOUD you can select the use of the sound version.
![image](https://github.com/kbaggen/iBLOPPER-ESP8266/assets/16992918/bba0844e-a9d1-46ab-aa1f-33e876811e19)

## Vibration version
Video: https://youtu.be/ms6W1qMlyHk

To build an iBLOPPER Vibration you need:

1x Wemos D1 Mini.
1x DS18b20 probe, 1 meter, + resistor (4.7K Ω Resistor)
1x MPU6050
1x Waterproof-Plastic-Electric-Project-Case-Junction-Box-55x35x15mm or or just a TickTax box.
![image](https://github.com/kbaggen/iBLOPPER-ESP8266/assets/16992918/1b55ac08-4edf-41ca-876a-b925ca18226b)


Below you find the diagram of D1 Mini build.
![image](https://github.com/kbaggen/iBLOPPER-ESP8266/assets/16992918/ab5c436a-764c-45d4-a59e-e2e43eb2036f)

