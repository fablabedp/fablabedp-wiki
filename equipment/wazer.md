# Wazer - Waterjet

**[Wiki Home](https://hackmd.io/@fablabedp/home)**

###### tags: `equipment` `waterjet`

![](https://i.shgcdn.com/6a05dcdc-e72a-4ebd-a6f5-b00e3988d401/-/format/auto/-/preview/3000x3000/-/quality/lighter/)

Cutting Area - 305 x 460 mm  
Kerf (width of cut) - 1.2 mm  
Abrasive Rate - 0.15 kg/min  
Abrasive Hopper Capacity - 13.5 kg  
Abrasive Material - 80 Mesh Alluvial Garnet  

https://wazer.com/product/tech-specs/  
https://wazer.com/materials/materials-specs/  
https://support.wazer.com/resources/maintenance/procedures-  

---

# Usage

## Preparation

1. If the water level is more than 6mm below the cutting bed, manually top up the tank using the bucket.
2. Check that the [drain filters](#cleaning-drain-filters) are clean.
3. Check that both the PRCDs are on with a green light.
4. Turn on the water tap and turn on the Wazer.
5. Check the low pressure system: `Setup & Maintenance > Input Output Check > Output Check > LP Pump`.
6. Check the high pressure system:
    - Remove the abrasive hose end from the cutting head, and raise the cutting head about 13mm above the bed.
    - `Setup & Maintenance > Input Output Check > Output Check > HP Pump`.  The water should change from a white irregular flow to a clear smooth stream.  Repeat if necessary.
7. Establish the water level:
    - Manually position the toolhead somewhere near the middle of the bed, and ensure the abrasive hose is still removed.
    - `Setup & Maintenance > Mantenance > Water Level Setup`
8. Replace the abrasive hose tube in the cutting head, and turn off the Wazer.

## Setup

1. Fix the material to the cutting bed. Try to avoid putting the screws near the toolpath, to avoid collisions with the cutting head.
2. Prepare the file in [Wazercam](https://wam.wazer.com/).
3. Make sure there is enough abrasive in the abrasive hopper.  There should be at least 10-20% more abrasive than the estimate given by Wazercam.  Each cup (250ml) is about 550g of abrasive.
4. Copy the gcode from Wazercam to the SD card, insert the card into the Wazer and turn on the Wazer.

## Cutting

1. `Select Cut File` and follow the instructions:
    - When homing, ensure that the cutting head is raised to avoid any obstacles such as the screws.
2. Once ready to cut, first select `Check Cut Extents` to confirm that the toolpath is in the correct location and does not extend beyond the material.  **This is important**, especially at slower cutting speeds, to ensure not to damage the pierce plate and the tank.
3. If needed, use `Move Origin` to reposition the toolpath.
4. Select `Cut Material` to start the job.

## Cleanup

Once you are done cutting for the day:
 - Turn off the water tap and turn off the Wazer.
 - Leave the door open.

**The Next Day**:
1. Brush and vacuum the dry abrasive residue.
4. Turn on the water tap and turn on the Wazer.
3. Raise the cutting head and run a [tank cleaning cycle](#Tank-Cleaning-Cycle) `Setup & Maintenance > Maintenance > Tank Cleaning`.
4. Remove the cover of the used abrasive buckets and select `Setup & Maintenance > Maintenance > Used Abr. Collect`.  Run the low pressure pumps until the stream goes from cloudy to clear, and then press `ok`.
5. Empty the used abrasive buckets.
6. Clean the [drain filters](#Cleaning-Drain-Filters).
7. Check that the abrasive hose end is mostly dry and unclogged.
4. Turn off the water tap and turn off the Wazer.

---

# Cleaning & Maintenance

![](https://github.com/fablabedp/fablabedp-wiki/raw/main/equipment/images/wazer_low_pressure_system.png)


## Cleaning everything above the water level

After doing some cutting there will be abrasive everywhere. the easiest way to clean it off is to leave the lid open a nd let it dry, then to brush/vacuum it off.

## Emptying the used abrasive buckets
https://www.wazer.com/how-to-videos/empty-used-abrasive-buckets

Should be emptied before every new cut.

## Cleaning Drain Filters
https://www.wazer.com/resources/maintenance/procedures/drain-filter-cleaning

It is recommended to clean the Drain Filter after every cut job.

Pull on fixture to remove each filter - dunk the filter in water (can use used abrasive buckets) - then rinse in sink.

## Tank Cleaning Cycle
https://www.wazer.com/resources/maintenance/procedures/tank-cleaning-cycle

Abrasive will normallly accumulate in the bottom of the tank.  there is a cleaning cycle that moves the toolhead along a predefined pattern to push abrasive towards the corners of the tank so that it can be collected by the pickup filters

It is recommended running this cycle before cutting if your machine has been sitting for a long time with abrasive in the bottom.  
Requires that there is a certain amount of abrasive accumulated in the tank, otherwise it will not have any effect.  
`Setup & Maintenance > Maintenance > Tank Cleaning`

## Cleaning the filtration system and collecting used abrasive
https://www.wazer.com/resources/maintenance/procedures/clearing-the-filtration-system  
https://www.wazer.com/resources/maintenance/procedures/abrasive-pickup-cleaning  

Should follow these steps if the filtration system does not seem to be collecting used abrasive at a normal rate.

`Setup & Maintenance > Maintenance > Used Abr. Collect`
 - Will run the low pressure pumps.
 - To try to clear a blockage, plug the outlet holes with your fingers for about 10s, once you release the water should become murkier.  repeat several times on one side and then the other.

`Setup & Maintenance > Maintenance > Abrasive Pickup cleaning`
- Will attempt to clear blockages around the pickup filters in the corners of the tank.

## Full tank cleaning

https://www.wazer.com/resources/maintenance/procedures/full-tank-cleaning  
https://www.wazer.com/resources/maintenance/procedures/venturi-clean-out  
https://www.wazer.com/resources/maintenance/procedures/tank-draining-siphon-method

https://www.wazer.com/resources/maintenance/procedures/rear-baffle-quick-check  
Rear Baffle blockage - this can cause the water level around the filters to drop relative to the level in the tank when running the low pressure pumps ("Used Abr. Collect") .  A full tank clean is needed to clear the blockage.

## Nozzle Purge
https://www.wazer.com/resources/maintenance/procedures/nozzle-purge

depressurize the high-pressure system - if the wazer was shutdown or turned off before completing a cut you must purge the high pressure system  
`Setup & Maintenance > Maintenance > Nozzle Purge`

> if a job finishes normally or is paused/cancelled normally then it should automatically purge?

## Maintenance on High Pressure line

Before detaching the high pressure tube, always open the HP valve to release any residual pressure  
`Setup & Maintenance > Input and output check> output check > HP Valve`

eg: https://www.wazer.com/resources/maintenance/procedures/replacing-the-orifice