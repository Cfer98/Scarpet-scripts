# Scarpet-scripts

# spline.sc
#### By Cfer89


# loft.sc
#### By Cfer89

A tool to select a parametric surface based on Bezier quadratic interpolation. The wand is the `phantom_membrane`. You can select points holding the wand and right or left clicking on block. Right click and left click have different effects. Right click is only used for extending the selection of a spline. Left click is used to start a new spline. The selected points are used by the script to render the corresponding surface. 
A selection is not a selection of a surface if there is only one selected spline or if each selected spline is composed by only 1 point. The `/loft paste <block> <replacement>` command will silently fail when used while there is not a proper surface selected. If the selection corresponds to a proper surface, the `/loft paste` command will sets (almost all) the block that collides with the surface.
