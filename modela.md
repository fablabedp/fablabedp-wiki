# Roland MODELA MDX-20

*CNC Plotter / Milling / Probing*

#### **Technical Specs**

> Build Area: 203.2 x 152.4 x 62.4 
> Max Weight: 1000 g

### Modeling Functions

>Chuck:  6 or 1/8in OEM
>Sindle motor: 10W
>RPM: 6500
>Accepted material: Wood, Plaster, Resin, Chemical Wood, Aluminum (A5052), Brass

## Scanning

> Sensor: Piezoeletric
> Method: Probing Contact, mesh
> Speed: 4 - 15mm/sec

## Interface

> Standard: RS-232C
> Baudrate: 9600 bps
> Data Bits: 8 bits


### Throubleshooting

- Doesn't operate:

  Is the STANDBY key on?  
  Press the STANDBY key.
  
  Has operation not been paused by pressing the VIEW key (lighting up the VIEW LED)?  
  Press the VIEW key to cancel the View state.
  
  Are the cables connected correctly?  
  Check MODELA outputs to make sure they are connected correctly.
  
  Is the cable for the connection with the computer suited to the MODELA and the computer?  
  For the cable, use a ptionally aveilable serial cable (such as XY-RS-34). A straight serial cable suchb as is commonly used to connect a modem cannot be used.
  
  Are the settings for the computer and the software correct?  
  Check the following and make the correct settings.
  
  Data output port        :Port connected to any one of COM1 throught COM4  
  Communication parameters:Bit rate of 9600, no parity, one data bit, stop bit 8, and hardware handshaking
  Select output device    :MDX-15 or MDX-20

- Modeling mode LED/Scanning LED flashing (10x sec):

  Was the power switched on in the correct sequence?  
  First turn on the computer, then turn on MODELA.
  
  This indicates a communications error.  
  Switch off the power, then check the cable connections and the port setting for the driver.
  
  Was the computer restarted?  
  When the computer has been restarted, switch the power to the MODELA off, wait a few seconds, then switch it back on.

- All LEDs fashing slowly:

  Has the power cord come loose from the tool?  
  Switch off power and connect the cords to the jacks.

- Errors during printing

  - Speed drops during cutting  
  
  When cutting a workpiece of uneven hardness, such as wood, the MODELA may slow down automatically (to a minimum speed of 0.1mm). Once the MODELA has gone beyond the hard area, cutting continues at normal speed.
  
  - The standby LED is flashing slowly

  The workpiece cannot be cut, even when the speed is reduced. Switch the power off and back on.  
  Make sure the cutting tool being used is appropriate for the hardness of the workpiece in use. Modify the software settings to cut the workpiece a little at a time.

  - Actual tool moviment diffent than data

  If an attempt is made to cut more deeply then the rage of moviment for the MODELA allows, the tool automaticallyt rises to te uppermost point.  
  Check to make sure that the erpt settings in the cutting data are not too dseep, and that the tool extending from te sinde unit is not too short.

  - Correct cutting is impossible

  Are the tool, spindle, and workpiece all installed and loaded securely?  
  Rethighten ghe setting screw for the tool and the mounting screws for the spindle.

  - Unusual noise is heard from the spindle

  The spindle unit is a consumebla part. Replace with a new spindle after 700 hours of use.

  - The sindle motor does not run

  The sindle motor is a consumable part. Replace with a new spindle motor after 700 hours of use.

  - The VIEW LED is flashing slowly (1 sec. interval)

  Is the fornt cover emovet?  
  Install the front cover.  
  When a sensor unit is installed, The VIEW LED does not flash.

- Scanning LEDs flashing twice repeatedly:

- Unexpect Program Operation

  - I can't open a file
  - The included software doesn't function
  - If an error mensage appears

_All units in milimeters_


