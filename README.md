# Scarpet-scripts

# loft.sc
#### By Cfer89

A tool to select and make parametric surfaces based on Bezier quadratic interpolation.
The wand is the `phantom_membrane` (equivalent of wooden axe in worldedit).
You can select points holding the wand and right or left clicking on block.
Right click and left click have different effects:

-Left click is used to start a new spline

-Right click is only used for selecting a new point of an already existing spline


Splines are defined by one or more control points selected by the user (even if a spline is defined by only a single point, it is considered by the script as a spline). In a similar way (extending the concept of spline) you can consider a surface as a spline where the control points are all the splines the user has created. This creates a tridimensional parametric surface that will be eventually rendered by the script. (Splines are rendered as black lines during the selection)

Selecting the points in a different order makes a huge difference and can be a bit confusing at first, but this gives you more possibilities for customizing the surface shapes. By holding the phantom membrane and selecting nearby inventory slots, it is possible to decide where you exactly want to add or remove splines or points. A red cross is rendered on the selected point. If you do `/loft del spline` or `/loft del point` you will delete that spline or that selected point. 
A small green sphere is rendered in a point when that is the last point of a selected spline. Right clicking on block with a phantom membrane will extend the spline with a new control point. Same applies with the yellow sphere with the difference that right clicking on blocks with a phantom membrane will extend the spline in the other direction. And you can create new control points between 2 selected points when a green line is rendered between those 2 points.

Important: a selection does not corresponds to a proper surface if there is only one selected spline or if each selected spline is composed by only 1 point. The `/loft paste <block> <replacement>` command will silently fail when used while there is not a proper surface selected. If the selection corresponds to a proper surface, the `/loft paste` command will sets (almost all) the block that collides with the surface.
Notice that you could use this script to make thin splines by selecting 2 different splines that have the same control points. This is considered by the program as a proper surface. 
