Pocket NC

Edge finding

B Axis offset

Default offset of 0.885 in.
*insert* measured offset.

Turn on and home all axis

Measure tool and stock

Measure diameter of the edge finder tip (OEM is 0.200 in).

Measure your stock (material) and ajust the model to match the size.

Measure Tool Length Offset

Measure the machining tool length offset of the tools you will be using for machining the part.

When you are finished measuring tool length offsets, load the edge finding tool holder into the spindle and install the edge finding tool. You do not need to measure the tool length offset of the edge finder.

Don't forget the dowel pins if installing the vise

Collet order:

1 - Bottom tapered nut
2 - Collet
3 - Top tapered nut

Measure X offset:

First, measure the X offset. Use the manual controls to move the spindle alongside the stock on the outside (opposite from the A table side) of the stock. The edge finding tool should be parallel to the X face of the stock.

Bump the wobbler on the edge finder slightly so that it is not concentric with the shank. Turn on the spindle using the MIDI command G0 G90 M5 S1000. [Do not exceed the maximum speed for which the edge finder is rated.]

EDGE FINDER MAX. SPEED 2.000 rpm

Bumping the wobbler, with a finger or other object, while the spindle is turning is not recommended. 
Only adjust the wobbler position when the spindle is off.

Move the tool toward the face. Decrease the step size to 0.001 inches or less as you get close to the part. As the wobbler starts to touch the face it will start to spin more concentrically with the shank of the edge finder. Keep moving the edge finder toward the part until the wobbler spins concentrically with the shaft of the edge finder. Continue to move the edge finder closer to the part until you see the wobbler suddenly “jump” to a new position that is no longer concentric with the shank of the edge finder.

The tip will deflect when it touches the part.

Look at the Digital Readout (DRO) and record the X position.  

Type “G0 G90 M5” into the MDI window to stop the spindle.  

The offset is the X distance displayed in DRO minus half of the edge finder tip diameter. The calculation for the X offset is: (absolute value of measured X distance) - (½ edge finder tip diameter) = X offset.

Measure Y offset:

Move the spindle so that the edge finder is above the stock. The tool should be parallel to the Y face of the stock.

Bump the wobbler on the edge finder slightly so that it is not concentric with the shank. 

Turn on the spindle. [Do not exceed the maximum speed for which the edge finder is rated.]

Move the tool toward the face. Decrease the step size to 0.001 inches or less as you get close to the part. As the wobbler starts to touch the face it will start to spin more concentrically with the shank of the edge finder.

The tip will deflect when it touches the part.

Look at the Digital Readout (DRO) and record the Y position.

Type “G0 G90 M5” into the MDI window to stop the spindle.

The offset is the Y distance displayed in the DRO, minus half of the tool diameter. The calculation for the Y offset is: (Y distance) - (½ Edge Finder Tip Diameter) = Y offset.

Eg. Y offset = 1.2552  - 0.200/2 = 1.1552 inches.

Compare this measured Y offset with the distance between the origin and the Y face in Fusion. If they do not match, move the part in Fusion until the measured Y offset and the model Y offset match. 

[Do not adjust the size of the stock in CAD. Instead use the move commands to adjust its location.]

If the measured distance from the machine origin to the Y surface and the model value are significantly different before adjustment, and you have measured your stock and verified that the model dimensions match the physical dimensions, it means your machine origin in your model may be in the wrong location. Double check before proceeding.

Once the digital origin and the physical origin are coincident, generate and post-process the toolpaths.

[Do not move the stock after it has been located through the edge finding process. If the stock is moved, the edge finding process will have to be repeated.]

[] = disclaimers

[V2-10 Edge Finding Tutorial - User Resources - Confluence](https://pentamachine.atlassian.net/wiki/spaces/PNFUR/pages/368902313/V2-10+Edge+Finding+Tutorial)
