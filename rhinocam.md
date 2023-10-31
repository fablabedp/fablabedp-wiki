# RhinoCAM

**[Wiki Home](https://hackmd.io/@fablabedp/home)**

###### tags: `CAD` `CAM` `rhino` `cnc`

## Knowledgebases (kb)

- proprietary MecSoft file format
- saves machining operations from a project with all configurations 
- also stores tools
- loading a kb will import the setups/operations without any control geometry selected and no toolpath yet generated
- can import all operations from a kb to currect job in Machining Browser window (Program tab > Knowledge Base > Load KB).
- or can selectively load operations using Machining Objects window.  In this case does not load tools.
- can import tools only from kb in tools tab. can also selectively import specific tools.

## Tools library

`Qsync\FORMAÇÃO\CNC\RhinoCAM\Tools_FabLabEDP\`

`fablabedp_tools.xlsx`
 - editable list of all tools for CNC and seperate tab for quantities and other references
 - data from first tab also converted to fablabedp_tools.csv and fablabedp_tools.vkb

`fablabedp_tools_knife.xlsx`
 - seperate table for knife tools which have different parameters to spindle-based tools

`fablabedp_tools_user-defined.vkb`
 - tools with user-defined custom profiles, that can only be saved in knowledgebase file

### Editing the library

1. Edit `fablabedp_tools.xlsx` and then export the `tools` tab as a .csv file.
2. Load the csv into rhinocam in the machining objects window.
3. Save the tool library to `fablabedp_tools.vkb` to update the knowledgebase file.

- The 'quantidades' tab in excel is just for reference and is not used by rhinocam
- Column notes:
   - 'Shank Diameter' - Rhinocam considers the shank of a tool flush to the cut surface as a collision.  To avoid this, we can set the shank diameter slightly less than the tool diameter.
   - 'Tool #' - always 1 by default, and then changed on a job basis if needed.
   - 'AA > AL' - default feeds and speeds for the tool, but these will be overwritten if following these steps > [#Setting-Feeds-and-Speeds](#Setting-Feeds-and-Speeds).
   - 'Comments' - part number for reference
- Importing VEE type tools from .csv is a bit funky. 'Flute Length' in the csv will be interpreted as 'Shoulder Len.' and used to recalculate the tool diameter.  To get the correct values for the table:
   1. Import the csv with the measured flute length.
   2. Correct the tool diameter and re-export the csv, the flute length will now have the recalculated value from rhinocam and the tool diameter will be 0.
   3. Update the excel table with the recalculated flute length and set the tool diameter to 0.
- Tools with custom profiles must be edited in rhinocam and do not exist on the excel table.

## Feeds and Speeds

**Surface Speed**: Speed of cutting edge relative to material  
**Chip Load**:  Amount of material removed with each pass of the cutting edge  
**Feed Rate**: Speed of toolhead relative to material

Using Surface Speed and Chipload to calculate Spindle RPM and Feedrate:  
`Spindle RPM = surface speed / (PI * Tool Diameter)`  
`Feed Rate = Spindle RPM * No. Flutes * Chip Load`

Some reference values:  
[Fablab Speed and Feeds Calculator](https://pub.pages.cba.mit.edu/feed_speeds/)

### Materials Library

Material libraries can be used to automatically calculate approximate feeds and speeds.  These are loaded from a directory path that does not seem to be configurable:  
`C:\ProgramData\MecSoft Corporation\RhinoCAM 2022 for Rhino 7.0\Materials`

We have a custom library file here:  
`\Qsync\FORMAÇÃO\CNC\RhinoCAM\Materials_FabLabEDP\FeedsSpeedsDataMM_fablabEDP.xml`  
Copy this file to the directory used by RhinoCAM to use material settings from this library.

To add a new material to the library, add a new node between the `<FeedsSpeeds>...</FeedsSpeeds>` tags:
```
<Material>
   <Name>NEW_MATERIAL_NAME</Name>
   <TextureFile>texture.bmp</TextureFile>
   <FeedsSpeedsRecord>MILLING, CARBIDE, SURFACE_SPEED, FEED_PER_TOOTH</FeedsSpeedsRecord>
   <FeedsSpeedsRecord>MILLING, HSS, SURFACE_SPEED, FEED_PER_TOOTH</FeedsSpeedsRecord>
   <FeedsSpeedsRecord>MILLING, CERAMIC, SURFACE_SPEED, FEED_PER_TOOTH</FeedsSpeedsRecord>
</Material>
```
 - `texture.bmp` does not need to be edited, RhinoCAM does not seem to care if this texture file exists or not.
 - For `SURFACE_SPEED`(m/min) & `FEED_PER_TOOTH` (mm) you can use the *Fablab Speed and Feeds Calculator* as reference for some materials, choosing a tool diameter roughly similar to what will normally be used for this material.
 -  The parameters for `CARBIDE`, `HSS`, and `CERAMIC` can be identical unless some customisation is really needed here.

### Setting Feeds and Speeds

 - Default tool settings are defined in the tools library and imported automatically into a new operation when the tool is selected.
 - Preset Surface Speed and Chip Load values are stored in Material Files:
    `C:\ProgramData\MecSoft Corporation\RhinoCAM 2019 for Rhino 6.0\Materials`
    `FeedsSpeedsDataMM` (RhinoCAM defaults)
    `FeedsSpeedsDataMM_fablabEDP` (Custom values)
    Feedrates can then be automatically calculated based on the % weightings in defined in the RhinoCAM preferences (Feeds & Speeds > % s to use for transferring from computed cut feed)
    - Must first choose a Material File in Job Stock Material settings (Program > Material)
    - Can then generate the feeds either in operation configuration (Feeds & Speeds > Load from File) or in Tool settings (Feeds & Speeds > Load from File)

#### Reccommended Feeds and Speeds

Some suggested values adequate for most operations (via Feeds & Speeds > Load from File).

Milling operations:
- Spindle Speed: 18000
- Feedrate: 3500

Drilling operations:
- Spindle Speed: 7000
- Feedrate: 2000



## 4th Axis

In `General Parameters` of `Machine Tool Setup`:
- Make sure `Output all coordinates in local Setup Coordinate System` is deselected - ie: do not use any configured work zero - will use the world coordinate system as the work coordinate system.
- `Tool Change Pt` - define a point outside the area of rotation of the stock/workpiece to avoid collisions when the work rotates between processes (ie: via Rotate Table Setup), mainly when the workpiece is non-cylindrical.

## Errors

*"No Curves found! Cannot proceed"* when trying to select edges for Machining Regions
 - This error will appear if only polysurfaces are visible.  You need to have a curve visible somewhere, even though you can select polysurface edges as Curve Regions.