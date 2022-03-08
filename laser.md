# Laser Cutter

###### tags: `equipment` `laser` `inkscape`

![](https://github.com/fablabedp/fablabedp-wiki/raw/main/images/epilog-mini18.jpg)  
**Epilog Mini 24 60W**  
**Bed size 600 x 300mm**  


--- 

## 1. Cutting from Inkscape

### i. Prepare Drawing

Page Size (optional):
 - Set to custom size 600x300mm to match laser bed size, or alternatively, resize the page to the drawing extents.  This depends on how you intend to align your drawing to the material (see [Aligning the material](#ii-align-the-material-with-the-drawing)).

For lines to cut:
 - Set Fill to none.
 - Set Stroke Width to 0.01mm (greater than this, or setting to `Hairline`, and the line will be interpreted as raster and not vector)

For lines to engrave:
 - Set Stroke to none, if you don't want to include the stroke width in the engraving.

Things to try something is wrong with the drawing in the job preview:
 - Make sure all objects are paths, and not other object types such as ellipse, rectangle or text etc. - `Path > Object to Path`
 - Release/remove any clipping masks and ungroup any grouped objects.
 - Set Fill/Stroke colour to black (if not using Color Mapping).

### ii. Save as PDF

`File > Save As > File Type: Portable Document Format (*.pdf)`

*It is possible to print directly from Inkscape instead of from a pdf for raster engraving, but not for vector cutting.*

### iii. Open PDF and print

 - Printer: Epilog Engraver WinX64
 - Page Sizing & Handling: Actual size
 - Orientation: Landscape (if page size different to laser bed dimensions)

---

## 1. Cutting from Rhino

### i. Prepare Drawing

Line properties for lines to cut:
 - Linetype: Continuous.
 - Print Width: Hairline or Default.
 - Display/Print Color: Not important unless using color mapping.

### ii. Print

 - Printer: Epilog Engraver WinX64
 - Size: Custom Size
 - Output Type: Vector Output
 - Output Color: Not important unless using color mapping.  If using color mapping, choose the correct property based on how you configured your drawing (Colors can be specified as either Display or Print Color).
 - View and Output Scale:
    - select correct viewport
    - set cropping to `Window` or `Extents` (see [Aligning the material](#ii-Align-the-material-with-the-drawing))
      - click `Set` if window needs to be repositioned.
 - Scale: 100% 1:1
 - Margins: 0 for all margins
 - Position: Offset From Lower Left
 - Line Types and Line Widths, Line Width: Default line width 0.01mm

---

## 2. Set Laser Properties

Enter Printer Properties in print dialog:
 - Select job type
 - Set Piece Size - normally 600x300mm (machine bed size) (see [Aligning the material](#ii-Align-the-material-with-the-drawing)).
 - Options:
    - Auto Focus - Ensure is disabled **unless** a full sheet of material is being used, to avoid the probe getting caught in the honeycomb bed.
    - Send to Laser - will send the job directly to the machine.
    - Send to Manager - will send the job to the Epilog Job Manager, where settings can be confirmed or altered, and where you can see a preview of the cut.

### Vector Setting

Some recommended Settings from Epilog:  
|               |        | Speed | Power | Frequency |
| ------------- | ------ | ----- | ----- | --------- |
| MDF / Plywood | 3 mm   | 30    | 60    | 500       |
|               | 6.4 mm | 20    | 100   | 500       |
|               | 9.5 mm | 10    | 100   | 500       |
| Acrylic       | 3 mm   | 20    | 100   | 5000      |
|               | 6.4 mm | 12    | 100   | 5000      |
|               | 9.5 mm | 6     | 100   | 5000      |
| Leather       | 3 mm   | 50    | 80    | 5000      |
| Rubber        | ? mm   | 60    | 90    | 500       |

### Raster Setting

Engrave Direction: 'Bottom Up' may produce cleaner results  
Some recommended Settings from Epilog:  
|                    | 300 DPI |       | 400 DPI |       | 600 DPI |       |
| ------------------ | ------- | ----- | ------- | ----- | ------- | ----- |
|                    | Speed   | Power | Speed   | Power | Speed   | Power |
| MDF / Plywood      | 60      | 100   | 80      | 100   | 100     | 100   |
| Acrylic            | 100     | 50    | 100     | 40    | 100     | 30    |
| Anodized Aluminium | 100     | 55    | 100     | 45    | 100     | 35    |
| Glass              | 40      | 100   | 50      | 100   | 60      | 100   |
| Leather            | 100     | 40    | 100     | 30    | 100     | 20    |
| Mat board          | 100     | 65    | 100     | 55    | 100     | 45    |
| Rubber             | 20      | 100   | 30      | 100   | 40      | 100   |

## 3. Preview in Job Manager (optional)

The preview is useful to check which lines are will be cut, and which engraved, or to confirm color mappings.
 - On the preview tab, the position of the drawing can be edited. (`edit position` button in the bottom left corner).  The preview assumes the X-Y origin for the job is set to the machine origin, and always shows the full bed, regardless of the piece size defined in the print settings.
 - Cutting and engraving settings can be edited.

If changes are made to the job in the Job Manager, the job must be resent to the machine via the `Quick Print` icon.

## 4. Prepare Machine

### i. Ajust Focus

 - Disable X-Y motors - `X-Y Off > Go`
 - Position the laser head above the material and flip down the focus guage.  Use the up and down buttons to position the bed so that the material is just touching the bottom of the guage.
 - Flip the guage back up, and `Reset` to enable X-Y motors and return to home.

### ii. Align the material with the drawing

There are several ways to do this:
 - **Using full bed size** - In the Epilog print settings set your piece size to the dimensions of the machine bed, and position your drawing accordingly.  In this case make sure the X-Y home of the machine is set at the machine origin (top left corner).  This is the simplest option if you are using a full sheet (600x300) of material.
 - **Using custom material size** - In the print settings set your piece size to the size of your material, and align the X-Y home with the top left corner of the material (can also use the machine origin).  This is useful if using smaller pieces of material and want to see how your design fits the material in the preview.
 - **Using drawing extents** - Resize your page to your drawing (Inkscape) or set output scale to `extents` (Rhino) to align your drawing to the page origin (top left corner).  After sending the job to the machine, set the X-Y home to where you want to cut your drawing.  This is useful when alignment relative to the material is not crucial, such as experimenting with small cuts or making use of offcuts.

Setting the X-Y home:
- Disable X-Y motors - `X-Y Off > Go`
- Enable laser pointer - `Pointer`
- Position the laser head and set as home - `Set home`

## 5. Start Cutting

- Turn on extraction
- Turn on air pump (unless only doing raster engraving, see [Air Assist](#Air-Assist))
- Select job - `Job > up/down`
- Ensure lid is closed and start cutting - `Go`

**Never leave the laser cutter unattended while cutting.**


## Air Assist

Using air assist is normally not necessary for raster engraving, and may provoke uncessary circulation of particulates inside the machine.  It is disabled by default for raster jobs, but can be activated in the config menu on the machine (if you enable this setting, you will need to re-send your job to the machine for it to take effect).

If doing a raster-only job with default settings, you do not need to turn on the air pump.


## Centering

With the `Center-Engraving` option selected, the machine will center the drawing at the X-Y home (all cuts, not just engravings).

Selecting this option will put an asterisk next to the job name on the machine.

![](https://github.com/fablabedp/fablabedp-wiki/raw/main/images/center_engraving_option.png)
![](https://github.com/fablabedp/fablabedp-wiki/raw/main/images/center_engraving_display.jpg)

 - `Center-Center` - Will center the drawing at the X-Y home, based on the drawing extents.  Page size will be ignored.
 - `Page-Center` - Will center the page as defined by `Piece Size` at the X-Y home.  This might be useful if you require non-uniform margins that are not represented by the drawing extents.
 - `Left-Center` and `Top-Center` - These do not seem to work on our machine.  Trying to run the job gives the error "Job Not Ready Yet"

**IMPORTANT** - *Do not run a centered job without positioning the X-Y home away from the machine origin, as the machine will attempt to cut the job ignoring the axis limits and crashing the head.  This seems to be a bug.*
 
*The Centering option does not seem to affect the job preview, ie: the preview does not represent the result.  If the drawing position is edited in the preview, this will offset the drawing from the center position defined by the X-Y home.*


## Color Mapping

Color mapping can be used to have different cut properties for different lines within the same job.

 - Any colors can be used, but the R,G,B values must exactly match those defined in the print properties Color Mapping tab.
 - Black cannot be used for color mapping, any black lines or fills will use the cut properties defined on the General tab.
 - Any colors in the drawing that do not match those listed in the Color Mapping tab will also be interpreted as black.
 - Air assist will only work for raster engraving color-mapped lines if raster air assist is enabled in the machine config menu.
 - In the Epilog Job Manager, the color mapping tab will list all the colors found in the drawing matching those defined in the print settings.  If a color is defined in the print settings but not found in the drawing it will not list it, *with the exception of the first color in the list (a bug?)*.