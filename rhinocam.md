# RhinoCAM 

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

`fablabedp_tools_user-defined.vkb`
 - tools with user-defined custom profiles, that can only be saved in knowledgebase file

### Editing the library


## Feeds and Speeds

**Surface Speed**: Speed of cutting edge relative to material
**Chip Load**:  Amount of material removed with each pass of the cutting edge
**Feed Rate**: Speed of toolhead relative to material

Using Surface Speed and Chipload to calculate Spindle RPM and Feedrate:
`Spindle RPM = surface speed / (PI * Tool Diameter)`
`Feed Rate = Spindle RPM * No. Flutes * Chip Load`

Some reference values:
https://pub.pages.cba.mit.edu/feed_speeds/

### Setting Feeds and Speeds

 - Default tool settings are defined in the tools library and imported automatically into a new operation when the tool is selected.
 - Preset Surface Speed and Chip Load values are stored in Material Files:
    `C:\ProgramData\MecSoft Corporation\RhinoCAM 2019 for Rhino 6.0\Materials`
    `FeedsSpeedsDataMM` (RhinoCAM defaults)
    `FeedsSpeedsDataMM_fablabEDP` (Custom values)
    Feedrates can then be automatically calculated based on the % weightings in defined in the RhinoCAM preferences (Feeds & Speeds > % s to use for transferring from computed cut feed)
    - Must first choose a Material File in Job Stock Material settings (Program > Material)
    - Can then generate the feeds either in operation configuration (Feeds & Speeds > Load from File) or in Tool settings (Feeds & Speeds > Load from File)