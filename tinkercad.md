# Tinkercad

###### tags: `tinkercad` `3d`

![](https://github.com/fablabedp/fablabedp-wiki/raw/main/images/tinkercad.jpg)  

### Navigation

 - `right click` to rotate the view. `middle click` or `shift + right click` to pan.
 - `F` - Fit the selected objects to the view.
 - Controls on left side for changing the view, including a button to change to an orthographic view.  Orthographic view is recommended for most cases, using the view cube to enter 2D views.

### Transforming Objects

 - `arrow keys` - Translate object in X or Y, or hold `crtl` for Z.  Hold `shift` for fast move.
 - `D` - Drop the object to the workplane.
 - Drag to translate an object on the workplane, hold `shift` to constrain movement to the X or Y axis. Drag the Z arrow to reposition the object off the workplane.
 - Drag corner handles to scale an object.  Hold `shift` to maintain proportions, and/or hold `alt` to scale about the object center on the workplane.
 - These transformations normally snap to the grid.  The default is grid size is 1mm, but can be adjusted or disabled.
 - Drag curved handles to rotate an object. Hover over the inner circle for 1/16 (22.5°) snaps, and the outer circle for free rotation. Hold `shift` for 1/8 (45°) snaps.

### Using dimensions

 - After any transformation operation, dimension boxes will appear, that can be edited to more accurately define the transformation.

### Placing objects

 - Normally new objects are placed on the workplane, but when hovering over an existing object, they can be placed on a face of that object.  You can use `C` to disable this feature to place on the workplane instead.
 - If you place a new object on a face of an existing object, a green workplane will appear on the selected face.  You can then reposition the new object on this workplane if needed.  This workplane will disappear when you click off the object.

### Object properties

 - Different types of objects have different properties, shown in the inspector window.  Some object types are more customisable than others.  These parameters can be changed at any time.
 - Dimensional properties represent the object before any other transformations have been applied.  If you scale or deform an object, this will not effect the dimensional values in the object inpector.
 - Any geometry built in tinkcad is made up of straight edges and flat surfaces.  "Curved" surfaces are divided into flat segments, and most of the main object types with curved surfaces have an adjustable resolution for this (such as `steps`, `sides` or `segments`).

### Combining objects

 - Any object can be defined as `solid` or `hole`, and combined with other objects in a group.  After grouping, the hole objects are hidden, and only the resulting solid geometry remains visible.
 - You can put groups inside other groups, which can be useful for organising more complex geometries.
 - You can double click a group to enter inside it and edit its individual components, and then exit the group by clicking outside it.  You can't however, enter into a subgroup of a group, to do this you need to first ungroup the larger group.  A red shadow will appear around a group when you enter it.

### Visibility

 - `ctrl + H` - You can hide objects in the inspector window, to reshow a hidden objects there is a 'show all' button `ctrl + shift + H`.
 - `ctrl + L` - You can also lock/unlock objects in the inspector window. A locked object cannot be edited, and shows a purple outline when selected.

### Aligning objects

 - `L` - If more than one object is selected, you can use the align tool to reposition the objects to be aligned left, right or center in any of the X, Y or Z axes.
 - By default, it will reposition the objects relative to the overall left, right or center position of total area of all the objects selected.  Alternatively, you cant `ctrl + click` on any individual object to align relative to that object.

### Mirror

 - `M` - The mirror tool can be used to mirror the selected objects in the X, Y or Z axis.

### Cruise

 - `C` - You can use the cruise tool to reposition an object as if you are adding it as a new object, whereby it can be placed onto a face of another object.

### Duplicate

 - `ctrl + D` - Duplicate will copy an paste the object in the same position, which is useful for contructing aligned shapes.
 - If you apply transformations to a duplicated object, and then duplicate this new object, it will reapply the same transformations to the next object.  This is useful for creating patterns.

### Workplanes

 - It is possible to temporarily change the workplane position using the workplane tool, by selecting the face of an object.
 - All transformations, including align and mirror operations, will be done relative to new workplane.
 - To restore the default workplane, click anywhere in the background with the workplane tool.
 - Note that the grid cannot be precisely positioned when using the workplane tool, so the align tool needs to be used for precise dimensioning in this case.

### Rulers

 - A Ruler can be added as a reference point, so that when selecting an object, the position can be defined relative to the reference point.
 - You can toggle between `use endpoint` and `use midpoint` for a ruler.  The `use midpoint` option is useful for dimensioning objects relative their center, which is normally not the case.

### Types of objects

 - Many of the objects in the tinkercad library have more of a decorative purpose, or have limited use due to a lack of configurability.  Some of the more useful ones are:
    + `Box`
    + `Cylinder/Polygon`
    + `Sphere`
    + `Cone`
    + `Pyramid`
    + `Wedge/Roof`
    + `Tube`
    + `Torus`
    + `Paraboloid`
 - Some shapes are defined by a 2D drawing, such as:
    + `Extrusion`
    + `Revolved adjustable shoulder`
    + `Scribble`
    + `Text`
 - It is also possible to import a 2D vector SVG file to create 3D geometry.
    + Via the import menu, this will create an extrusion of the vector shape.
       * This is useful for importing text or other graphic elements for adding to a model surface.
    + With the `SVG revolver` object.
 - Some more complex useful objects are:
    + `Bent Pipe`
    + `Spherical Shell`
    + `Spring`
    + `ISO metric thread`


## Keyboard Shortcuts

https://www.tinkercad.com/blog/keyboard-shortcuts-for-the-3d-editor

PC => MAC  
`Ctrl` => `Command`  
`Alt` => `Option`  

### Viewing 3d Space

|  |  |
| --- | --- |
| Pan   | `Middle mouse` |
| Orbit | `Right mouse` |
| Zoom in or out | `-` and `+` or `Scroll` |
| Fit selection into view | `F` |
| Place Workplane   | `W` ( + `Shift` to flip ) |
| Place Ruler | `R` |
| Add Note | `N` |

### Move, Rotate, And Scale

|  |  |
| --- | --- |
| Move step on Workplane (X/Y axis) | `Arrow keys` |
| Move up step (Z axis) | `Ctrl` + `Up` / `Down` |
| 10x move step (X/Y axis) | `Shift` + `Arrow keys` |
| 10x move step (Z axis) | `Shift` + `Ctrl` + `Up` / `Down` |
| Rotate snap 45˚ | `Shift` + `Rotate Handle` |
| Uniform scale | `Shift` + `Scale Handle` |
| Scale about center | `Alt` + `Scale Handle` |
| Align | `L` |
| Mirror or Flip | `M` |

### Commands

|  |  |
| --- | --- |
| Drop to Workplane | `D` |
| Select multiple | `Shift` |
| Select all | `Ctrl + A` |
| Copy / Paste | `Ctrl + C` / `Ctrl + V` |
| Drag a copy | `Alt` + `Move shape` |
| Duplicate & repeat | `Ctrl + D` |
| Undo action | `Ctrl + Z` |
| Redo action | `Ctrl + Shift + Z` / `Ctrl + Y` |
| Delete | `Del` |

### Shapes Properties

|  |  |
| --- | --- |
| Group / Ungroup | `Ctrl + G` / `Ctrl + Shift + G` |
| Make a hole | `H` |
| Make a solid color | `S` |
| Make transparent | `T` |
| Lock or Unlock | `Ctrl + L` |
| Hide | `Ctrl + H` |
| Show all | `Ctrl + Shift + H` |