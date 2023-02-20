# This file contains additional info about all the math behind the loft script.
work in progress

## Some math definitions:

Since the script is based on parametric curves and parametric surfaces, let's first define what are those:

a parametric curve is a function that returns a point in 3D space given 1 variable u

a parametric surface is a function that returns a point in a 3D space given 2 variables (u,v)

## General structure of a loft surface:

The basic equation of a simple quadratic bezier surface `S` is given by:

`S  =  (1-u)^2 * ( P00*(1-v)^2 + 2*A00*v*(1-v) + P01*v^2 ) + (1-u)*u * ( 2*B00*(1-v)^2 + 4*C00*v*(1-v) + B01*v^2 ) + u^2 * ( P10*(1-v)^2 + 2*A10*v*(1-v) + P11*v^2 )`

The surface is defined for every real value of (u,v). Since it's convenient to define the surface in a limited domain, we have to limit (u,v): `0<=u<=1` and `0<=v<=1`. `P00`, `P01`, `P10`, `P11` are the main 4 control point (in 3D space) of the surface. They are visualized as the 4 corners of the surface. `A00`, `B00`, `C00`, `B01` and `A10` are the remaining 5 control point that are placed outside the surface and they define the concavity of the surface.

