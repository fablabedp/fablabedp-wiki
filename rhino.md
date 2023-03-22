# Rhino

###### tags: `CAD` `rhino`

## Zoom Extents

`ZE` to zoom extents all  
`ZS` to zoom extents selected  


## Hotkeys for Selecting View

Some useful custom hotkeys for working in a single viewport. Set in `Rhino Options > Keyboard`  

| Key | Command |
| --- | --- |
| Ctrl+0 | `'_SetView _World _Perspective` |
| Ctrl+1 | `'_SetView _World _Top` |
| Ctrl+2 | `'_SetView _World _Front` |
| Ctrl+3 | `'_SetView _World _Right` |
| Ctrl+4 | `'_SetView _World _Bottom` |
| Ctrl+5 | `'_SetView _World _Back` |
| Ctrl+6 | `'_SetView _World _Left` |
| Ctrl+9 | `'_Plan` (view normal to current Cplane) |


## Projecting Contour Outline

1. Select object >`Make2D` (with scene silhouette)

2. Select the resulting lines >`CurveBoolean`
    - DeleteInput = All
    - CombineRegions = Yes
    - AllRegions


## Merging Vertices

Eg: Importing DXFs and lines are split into individual segments.

This is a manual method for turning line segments into closed curves:

1. `SelChain`
2. `Join`

## Set Camera to View

Save a new view in the Named Views Panel, can also access with `NamedView`

## Set Camera View Center

To manually set camera target position:

`View > Set Camera > Place target`


## Add thickness to Curves/Polylines/Edges

Can use custom display modes to change how objects are rendered.

`Settings > View > Display Mode` and copy an existing mode to use as starting point.

Eg: to change curve thickness `Objects > Curve > Curve Width`


## Fixing Bad Objects

_See: https://wiki.mcneel.com/rhino/badobjects_

`Check` to identify bad objects

1. Try `RebuildEdges`
2. Try to identify the bad surfaces of an object: `ExtractBadSrf`  
3. Try untrimming and then retrimming the surface:  
 - `Untrim` with `keep trim objects`
 - `Trim` using resulting curves to recreate the original surface
4. `Join` to recombine surfaces and `Check` resulting object

## Closing Open Polysurfaces

1. `SelChain` to select edges of the hole
2. `DupEdge` and `Join` to create curve from edges
3. `Patch` to make a surface from the curve (Set `Adjust tangency` as needed)
4. `Join` original polysurface with new patch surface and repeat for other holes

## Closing Open Meshs

0. Use `Dir` and `UnifyMeshNormals` to check normals and flip as necessary.
1. Ensure all faces are joined into single mesh with `Join`
2. Try a combination of `UnifyMeshNormals`, `RebuildMeshNormals`, `MatchMeshEdge`, `RebuildMesh`, `
CullDegenerateMeshFaces`, `AlignVertices`
3. If mesh is still open, analyse with `ShowEdges`.  If holes are identified, try closing them with `FillMeshHole` or `FillMeshHoles`
4. Once the mesh is closed, if necessary split into it's seperate closed shells with `SplitDisjointMesh`.