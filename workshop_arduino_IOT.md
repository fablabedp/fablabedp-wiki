# Workshop Arduino IOT


## Arduino Cloud

- [Arduino IoT Cloud Home](https://cloud.arduino.cc/)
- [Arduino IoT Cloud](https://create.arduino.cc/iot/)
- [Arduino IoT Cloud Documentation](https://docs.arduino.cc/cloud/iot-cloud)
- [Web Editor](https://create.arduino.cc/editor)
- [Arduino Iot Cloud Remote (Android)](https://play.google.com/store/apps/details?id=cc.arduino.cloudiot&gl=US)
- [Arduino Iot Cloud Remote (iOS)](https://apps.apple.com/us/app/arduino-iot-cloud-remote/id1514358431)
- [Manager for Linux](https://create.arduino.cc/devices) "Arduino Manager for Linux Devices"

#### "Device"
Hardware that is registered to your account and can send/recieve data with Arduino's servers.  In IoT Cloud you can see if a device is online, in which case it is connected and communicating something with the server.

#### "Thing"
Like a "Project".  Can be associated with a Device and specify network credentials for it.  Defines all the variables that are communicated between the device and Arduino's servers.  Creating a Thing automatically generates an Arduino Sketch that connects to the server and sends/recieves the data.  You can also specify a timezone for a Thing.  Data sent to the server is stored in the "Thing" (max 1 day on free account) and can be downloaded as CSV file

#### "Dashboard"
An interface to visualise and interact with data being communicated with any Devices registered with the account.


## Arduino Prime Bundle

https://docs.arduino.cc/retired/kits/IoT-prime  

### Arduino MKR WiFi 1010 "maker ten ten"

https://docs.arduino.cc/hardware/mkr-wifi-1010  
https://store.arduino.cc/products/arduino-mkr-wifi-1010  

- SAMD21G18A Cortex-M0 32-bit SAMD21
- ATECC508A crypto chip
- Nina W102 uBlox module for Wifi and Bluetooth
- RTC provided by SAMD21 (no battery for RTC?)
- JST battery connector (Li-Ion, or Li-Po)
- grove-like i2c connector (SHR-05V-S-B)
- **Operating voltage is 3.3V**
- Vin pin - input for regulated 5V (max 6V). disconnects USB power if connected
- 5V pin - unregulated output of VIN or USB power input
- VCC pin - outputs 3.3V via on-board voltage regulator
	+ if battery powered, outputs battery voltage instead of regulated 3.3V
- LED ON - on when powered by VIN/USB, not on when powered by battery
- LED CHRG - [has various meanings](https://support.arduino.cc/hc/en-us/articles/360016119199-What-is-the-meaning-of-CHRG-LED-different-states-in-MKR-boards)
- LED_BUILTIN is on D6
- RGB LED connected to Nina uBlox module.  [Can be accessed using the WiFiNINA library](https://docs.arduino.cc/tutorials/mkr-wifi-1010/built-in-rgb).

#### ATECC508

https://learn.sparkfun.com/tutorials/cryptographic-co-processor-atecc508a-qwiic-hookup-guide/all  

> At a very high level, the purpose of using this chip is to (1) verify that the message received actually came from the true sender and (2) verify that the data received was not tampered with. This technology is used in hyper-critical devices such as rocket launches, medical devices, two factor authentication keys (2FA), ink cartridges, garage door openers and car key FOBs.  

> Probably it's most important feature: this device can securely store a private ECC key. In fact, this private key will never be accessible - not even to you, the owner. It is created internally on the chip during configuration, and it can never be read from the chip (even if your de-capped the chip). Although you will never know it, you can still command the co-processor to use the secret private key to create a unique signature on some data. With this functionality, it can be used to securely authenticate a message in any kind of communication system. For example, between systems such as a node in an IoT system.  


### Arduino MKR ENV Shield

https://docs.arduino.cc/hardware/mkr-env-shield  
https://docs.arduino.cc/tutorials/mkr-env-shield/mkr-env-shield-basic  
https://www.arduino.cc/reference/en/libraries/arduino_mkrenv/  

- I2C and analog
- HTS221
	+ relative humidity and temperature
	+ high accuracy
	+ 20-80% rH (relative humidity)
- LPS22HB
	+ Barometric pressure
- TEMT6000
	+ Lux - ambient light sensor based on a epitaxial planar phototransistor
	+ 440 nm to 800 nm, peak sensitivity at 570 nm.
	+ Max 650 LUX (LUX is a measurement of how intense the light is for the human eye)
- VEML6075 
	+ ultraviolet UVA and UVB intensity
	+ (older versions only)
- Micro SD card slot
- Absolute pressure range: 260 to 1260 hPa (hectopascal)
- Humidity range: 0 to 100%
- Humidity accuracy: ± 3.5% rH, 20 to +80% rH (relative humidity)
- Temperature range -40 to 120 °C.
- Temperature accuracy: ± 0.5 °C from 15 to 40 °C.
- Lux range: 10 to 100,000 lux.
- UVA/UVB resolution: 16-bit; unit μW/cm2.
- UVIndex: 1 to 11+.


### Arduino MKR Relay Shield

https://docs.arduino.cc/hardware/mkr-relay-proto-shield  
https://docs.arduino.cc/tutorials/mkr-relay-proto-shield/mkr-relay-shield-basic  
https://store.arduino.cc/products/arduino-mkr-relay-proto-shield?queryID=6093b3560a1241e9d2e95e3600a087f6  

The shield provides two relays (Datasheet)  called RELAY1 and RELAY2 commanded by pin 1 and pin 2 respectively.

- Operating voltage 3.3V (supplied from the host board)
- Max. operating voltage: 24 VAC, 50 VDC
- Max. operating current: 1 A
- Max. switching capacity: 62.50 VA, 30W



## Tutorials

_**Retired** - Some elements are out of date_

### IoT-Prime Experiment 1: Get to know the kit
https://docs.arduino.cc/retired/getting-started-guides/IoT%20Prime%20-%20Experiment%2001  

- serial print all sensor readings
- challenge: visualise temperature usings 4 different coloured LEDs

### IoT-Prime Experiment 2: Ways of graphing your data
https://docs.arduino.cc/retired/getting-started-guides/IoT%20Prime%20-%20Experiment%2002/  

- visualize temp & humidity readings on serial plotter
- save serial stream to csv file using coolterm
- import csv into libreoffice and make a graph
- challenge: add a timestamp and use a x-axis values

### IoT-Prime Experiment 3: Store data in memory cards
https://docs.arduino.cc/retired/getting-started-guides/IoT%20Prime%20-%20Experiment%2003/  

- print all sensors readings to a file on SD card
- challenge: add a start/stop button or something

### IoT-Prime Experiment 4: Connect to the Arduino Cloud
https://docs.arduino.cc/retired/getting-started-guides/IoT%20Prime%20-%20Experiment%2004  

- Intro to Arduino IOT Cloud
	+ how to make a "thing" (looks like arduino iot cloud did not distinguish yet between "thing" and "device")
	+ add temperature and humidity read-only variables
	+ create sketch and add network credentials, ENV shield library and code for initialising and reading the sensors
	+ create a dashboard and add some widgets to see the sensor readings
	+ challenge: add the remaining sensors to the dashboard, log data to an SD card

----


## Outline

1. What is arduino, introduction to the MKR1010 and Prime Bundle
	- > show some example arduino projects
2. Use offline Arduino IDE to program the board
	- Output all sensor readings to Serial monitor
	- use RGB LED to monitor humidity
	- 
	> overview of IDE
	> sketches and sketch folder  
	> board and serial port selection  
	> compilation and uploading  
	> serial monitor and plotter, Serial.begin(), Serial.println()  

_--- break ---_


example blink

example fade

seperate sketch for pwm with led then join with sensor

3. Digital IO Basics
	- attach LED via breadboard 


3. Expand the example
	- Connect piezo using breadboard and use as high temperature alarm
	- Experiment with mapping piezo/LED output to different sensor inputs
	> MKR1010 pinout, digitalIO, analog input, VCC, VIN, GND  
	> code structure, {}, ;
	> setup(), loop()  
	> variables (ignoring data types)  
	> functions  
	> pinMode(), digitalWrite(), analogWrite()  
	> if/else, map(), delay()  
	> libraries  

_--- lunch ---_

4. What is IOT, introduction to Arduino Cloud IoT  
	- > show some example IoT projects

5. Make an account, register new Device

6. Make new Thing
	- add variables for lux, temperature, humidity and pressure
	- select device, add network credentials
	- open in Web Editor and copy/paste remaining code from prepared example
	- upload to board
	 > variable data types  
	 > overview of Web Editor, explain difference between "stand alone" sketches, and sketches created with Thing on IoT Cloud, compile time limitation of free accounts  
	 > Arduino Create Agent  
	 > different tabs correspond to files (download sketch into sketch folder for example)  
	 > thingProperties.h, sketch.json, ReadMe.adoc, Secret  

7. Make a new Dashboard and visualise sensor readings
 	- add Thing for shortcut to access all variables
 	- experiment with other widgets to vizualise the readings
 	- explore all the widgets to understand what kind of inputs/outputs are possible with the device

8. Connect power supply and LED lamp via Relay Shield
	- add new variable to Thing
	- add code from second example to Thing sketch
	- update dashboard with switch and led to control/monitor the lamp

_--- break ---_

(extras)

- Play with Arduino IoT Cloud Remote
- Add a second Device, create a second Thing and synchronise the luz variable (https://docs.arduino.cc/cloud/iot-cloud/tutorials/thing-to-thing)
- Add additional LEDs for monitoring different sensors
- Log data to SD card
- Program the RTC and add time stamps to the data
- Visualise data in excel from csv file


----

### student test login

user: `ulrapktyepavvkbeje`  
pass: `testtest`