Rotated Work Offsets Tutorial

Pocket NC’s Rotated Work Offsets feature allows users to set a work coordinate system (WCS) origin that is relative to a point on a part or its stock, instead of a point that is relative to the machine (typically the center of rotation).
This allows the stock to be loaded onto the machine differently than it is modeled in the CAM workspace while maintaining the ability to perform positional 5 axis tool paths, otherwise known as 3+2 machining. 

[This tutorial is made for Fusion 360 other CAM software might work similarly.]

Step 1: CAM Setup

Create a new setup

orient the part the way it will sit on the machine when the A and B axes are at 0 degrees.

use “Select Z axis/plane & X axis” to orient the WCS the way the machine’s axes are oriented in relation to front facing the machine.

Pick your preferred origin point for the WCS.

Below, the corner of the stock that is closest to the spindle and the front of the machine has been chosen for ease of access.

move to the “Stock” tab.

begin defining your stock and its position relative to the part.

Lastly, move to the “Post Process” Tab.

In this example, we are using WCS offset 1 because we want to use the G54 code to define our work offsets on the machine. 
You may use any number from 1 to 8 here, just make sure you are aware of what G5x the number corresponds to. 

Step 2: Tool Path Application

Now that the setup is configured correctly, tool paths can be applied.
Tool paths and machining operations can be configured using the same method used when programming around center of rotation. 
The only difference will be where the WCS is displayed relative to the model, but [as long as it is oriented the way it needs to be to cut the desired feature], there will be no effect on the final tool path.

Step 3: Post Processing

After creating all the tool paths and the part ready to cut, it is time to post process them into g-code.

Begin by right clicking on the setup that was created in step one, in this example we have named it “Setup 1”, and then select “Post Process”.

Adjust your post processor window following the settings shown below.
The program number and program comment can be whatever you would like. 

In the "Properties" section, in the WCS parameter choose a virgin WCS meaning that it can't be already in use.
You can check if they are assigned in the Post Processor tab of of your program’s setup.  

Next, locate the property titled “Machine Model” and select the model of Pocket NC machine that this program will be run on. 

Finally, post process the g-code by clicking “OK” or “Post”.

It is good practice to keep the .ngc file extension on the file name.

Step 4: Machine Set Up

After g-code generation, the machine has to be set up. The majority of this process is the same as setting the machine up to cut a part that is programmed around the center of rotation:

-Turn on the machine and home its axes. 

-Install necessary fixtures.

-Install and measure the tools that will be used.

-Install the stock material, locating it on the fixture in the orientation that was planned at the start of the CAM programming.  

Step 5: Setting Work Offsets

*link to paper method*

Step 6: Simulate and Run
