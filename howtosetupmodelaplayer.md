# How to setup Modela Player

[Do not use modela player for PCB]

Modela has a dedicated software for the Roland Modela MDX-20 in which you have access to the materials available and you can define your tool arsenal.
The software also allows you to prepare your model to be machined.

Step 1: Open Modela Player

Step 2: Select the machine

Go to [File] and click on [Select machine...] a new window will appear

Define the following:

Model name: MDX-20

Command set: RML-1

Spindle Unit: Standard

Printer Name: Find "Roland MODELA MDX-20"

Step 3: Go to [File] and select [Open]

It will open a File Explorer window in which you will select the model to input in the player.
Modela Player allows the following formats: .mpj, .dxf, .igs, .mdj .

Step 4: Go to [Set] and select [Model]

Now we are going to define the model orientation and it's origin.

In the Size and Orientation tap make sure of the following:

Model Size: Length

Check if the model dimentions are accurate and keep the ratio.

If the model was't modeled in the way that respects the coordinates make use of the Orientation area to define the top surface by clicking on the dot that shows the right position in relation to the X/Y axis.

Go to the [Origin] tab

You can see that in an simple way it allows to select the model origin, simply click the dot to define the origin.

It is recommended to select the lower left corner.

Click [Ok]

Step 5: Make sure the tools needed for the job are defined in the [Add/Remove Tool] option.

If the tools selected for the task aren't already in the library please insert them as specified below:

-Go to [Options] and select [Add/Remove Tool] a window will pop up.

-Select [New].

A new tool slot will appear, in there you can select the parameters acording to the specs of the tool.

-Give your tool a name, please keep the following pattern: *tool diameter* *type of tool tip* eg: 1mm Square

-Define the tool material.

Tipically the material is HSS (High Speed Steel).

The CC (cemented carbide) is usually a speciallity material and more expensive.

- Set the flute diameter. 

- Click on [Cutting Parameters...]

- Select the material through clicking on the list in front of the material.

- Click on [Set Parameters]

- Double check the cutting parameters and feel free to ajust acording the material of coice.
  It is recomended to leave them at default.

- Oficialize the parameters by clicking on "Register" 
  Now your tool is ready

Step 6: Defining a new process

This will allow you to choose the order and which processes you would like to make.
It is recommended to respect the following order: Surfacing -> Roughing -> Drilling* -> Finishing**

* *Drilling depends on the part it can be ignored if not needed.
  ** - It is recommended to make a finishing process only after the part as been machined to that stage. 

Select the New process button with a ladder figure.

A window will appear with the following options:

- Surfacing

- Roughing

-  Finishing

-  Drilling

As the processes are very similar setup-wise the following will be a generic follow-through in that new window.

- Choose the type of process

- Select the cutting surface

- Choosing the tool for the process

- Select the area and depth 

- Choose the type of tool path to create

- Select the cutting parameters

- Entering a name for the process
