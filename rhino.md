# Rhino

###### tags: `CAD` `rhino`

## Projecting contour outline

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


## Set Camera View Center

To manually set camera target position:

`View > Set Camera > Place target`