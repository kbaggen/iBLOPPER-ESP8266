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

Videos:
https://youtu.be/XYqAmXFoWy8
https://youtu.be/rfGtCtaYLWA



