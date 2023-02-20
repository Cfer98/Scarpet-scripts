# This file contains additional info about all the math behind the loft script.
work in progress

## Some math definitions:

Since the script is based on parametric curves and parametric surfaces, let's first define what are those:

a parametric curve is a function that returns a point in 3D space given 1 variable u

a parametric surface is a function that returns a point in a 3D space given 2 variables (u,v)

## General structure of a loft surface:

The basic equation of a simple quadratic Bezier spline `s` is given by:

`s = P0*(u-1)^2 + 2*A0*u*(u-1) + P1*u^2`

It's convenient to limit `s`: `0<=u<=1`. In this way the Bezier spline is mapped by the parametre u in a segment of length 1 (`s(0)=P0` and `s(1)=P1`).
`A0` is a parametre that defines the concavity of the spline. A generic spline is composed by more Bezier splines. Since the spline has to be smooth, it's possible to calculate `Ai` coefficients by forceing the first derivative of a Bezier spline to match the first derivative of the following spline in the contact point. And since the problem is still undetermined, it's convenient to force the second derivative of the first spline to match the second derivative of the second spline. This results in a set of equation that can be solved and the solution is:

`A0 = 0.25 * (P0-P2) + P1` and `Ai = 2 * Pi - A(i-1)` for `i>0`

If the spline is defined by only 2 point, it's equation will be simply: `s = P0*(1-u) + P1*u`. And if the spline is composed by only one point, it will degenerate in a single point.

............................................................................

The basic equation of a simple quadratic Bezier surface `S` is given by:

`S  =  (1-u)^2 * ( P00*(1-v)^2 + 2*A00*v*(1-v) + P01*v^2 ) + (1-u)*u * ( 2*B00*(1-v)^2 + 4*C00*v*(1-v) + B01*v^2 ) + u^2 * ( P10*(1-v)^2 + 2*A10*v*(1-v) + P11*v^2 )`

The surface is defined for every real value of (u,v). Since it's convenient to define the surface in a limited domain, we have to limit (u,v): `0<=u<=1` and `0<=v<=1`. `P00`, `P01`, `P10`, `P11` are the main 4 control point (in 3D space) of the surface. They are visualized as the 4 corners of the surface. `A00`, `B00`, `C00`, `B01` and `A10` are the remaining 5 control point that are placed outside the surface and they define the concavity of the surface. It's an easy task to show that the `S(0,0)=P00`, `S(0,1)=P01`, `S(1,0)=P10`, `S(1,1)=P11`. So it's like (u,v) maps the surface in a cartesian plane.

A generic loft surface is composed by a grid of `n * m` main control points. If `n * m = 2 * 2`, the loft is composed by only one quatratic surface. In general `n>=2` and `m>=2`. In this case the loft is composed by `(n-1) * (m-1)` quadratic surfaces. The first task of the script is collecting the main control points of the surface. Those points are organized in an string of `m` splines inside the variable `global_loft:'sets'`. Each spline is composed by a string of control points. In general each spline doesn't have the same number of control points and that problem has to be solved so that all the control points can be arranged in a `n * m` grid. `n` is calculated as the max number of control point of all the splines. If there are 2 splines and one of them is composed by 5 control points and the other is composed by 3 control points, `n=max(5,3)=5`.





