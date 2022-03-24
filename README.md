# Scarpet-scripts

# loft.sc
#### By Cfer89

A tool to select and make parametric surfaces based on Bezier quadratic interpolation.
The wand is the `phantom_membrane` (equivalent of wooden axe in worldedit).
You can select points holding the wand and right or left clicking on block.
-Right click and left click have different effects:
-Left click is used to start a new spline
Right click is only used for extending the selection of a spline
Splines are defined by one or more control points selected by the user (if a spline is defined by a single point, even if it is technicaly considered by the script as a spline, it is not really a spline but just a dot). In a similar way (extending the concept of spline) you can consider a surface as a spline where the control points are all the splines the user has created. This creates a tridimensional parametric surface that will be eventually rendered by the script during the selection of points.
Selecting the points in a different order makes a huge difference and can be a bit confusing at first, but this gives you more possibilities for customizing the surface shapes.
Important: a selection does not corresponds to a proper surface if there is only one selected spline or if each selected spline is composed by only 1 point. The `/loft paste <block> <replacement>` command will silently fail when used while there is not a proper surface selected. If the selection corresponds to a proper surface, the `/loft paste` command will sets (almost all) the block that collides with the surface.
Notice that you could use this script to make thin splines by selecting 2 different splines that have the same control points. This is considered by the program as a proper surface. 
