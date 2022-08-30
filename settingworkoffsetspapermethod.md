Setting Work Offsets (Paper Method):

This is a manual intervention step where the machine is told what point all of the g-code coordinates originate from.
There are several ways to perform this process but in this example we are going to use the simple touch-off/paper method. 

Install the tool (usually an endmill) you wish to use for this process. 
It is recommended that the tool has three or more flutes for better functioning.
In the source example they use a 1/8” single-flute endmill turned inwards the tool holder.

Measure the inserted tool.
If the tool being used to set work offsets is not a tool that will be used in the program you will need to pick a empty tool number slot. 

Setting Z Work Offset

Take advantage of the jog control to aproach the tool to the right side of the stock inside it's front face.

For the DRO readout to be accurate we need to call out the TLO "G54 G43 Hx" through the command input.

Note: The Gcode “H” value must match the tool number used for the touch-off tool.

Making use of the 0.1 precision bring the tool closer to the stock.

[Be careful not to go too far and collide the tool with the stock.]

Once it's close enough increase the precision by using the 0.001 scale and with the aid of the calibration paper move the tool until the paper has been pinched.

Note: Feel free to go as far as 0.0001 scale for greater precision.

in the interface go to "Tooling" and in the “Work Offsets" tab  click on the input box in the Z row and G54 column.
Select “Zero DRO”.

Note: You can select “Set DRO to a Value” and then entering the thickness of the paper and the new DRO value has a more accurate offset.

Setting the X Work Offset

Take advantage of the jog control to aproach the tool in front of the stock and just below the top of the stock. 

Making use of the 0.1 precision bring the tool closer to the stock.

[Be careful not to go too far and collide the tool with the stock.]

Once it's close enough increase the precision by using the 0.001 scale and with the aid of the calibration paper move the tool until the paper has been pinched.

Note: Feel free to go as far as 0.0001 scale for greater precision.

in the interface go to "Tooling" and in the “Work Offsets" tab  click on the input box in the Z row and G54 column.
Select “Set DRO to a Value”.
You will need to insert the negative of the radius of the choosen tool, meaning that value is how far the center of the tool is offset from the face of the stock in the negative direction.

Note: Include the thickness of the paper in the new DRO value for a more accurate offset.

Setting Y Work Offset 

Take advantage of the jog control to aproach the tool on top of the stock near the front corner of the stock. 

Making use of the 0.1 precision bring the tool closer to the stock.

[Be careful not to go too far and collide the tool with the stock.]

Once it's close enough increase the precision by using the 0.001 scale and with the aid of the calibration paper move the tool until the paper has been pinched.

Note: Feel free to go as far as 0.0001 scale for greater precision.

in the interface go to "Tooling" and in the “Work Offsets" tab  click on the input box in the Z row and G54 column.
Select “Set DRO to a Value”.
You will need to insert the negative of the radius of the choosen tool, meaning that value is how far the center of the tool is offset from the face of the stock in the negative direction.

Note: Include the thickness of the paper in the new DRO value for a more accurate offset.
