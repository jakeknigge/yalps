# yalps
This suite of functions is called yalps---**y**et **a**nother **l**inear **p**rogram **s**olver.
It solves small to moderate standard form linear programs (LPs) using the barrier method.
```
Solving standard form LP (and its dual)
      primal                    dual
      minimize     c'*x		    maximize     -b'*nu
      subject to   Ax = b 		subject to   A'*nu =< c
                   x >= 0
with variables
	x, c \in R^n
	A \in R^{p, n} with p < n (i.e., A is a fat matrix)
	b, nu \in R^p
```
The barrier method repeatedly solves a centering problem with scalar parameter `t`, that is
increased at every iteration of the algorithm.
```
Solve the LP via the centering problem
      minimize     t*c'x - sum(log(x))
      subject to   Ax = b
```
The current implementation is for Matlab; a Julia implementation will be posted soon.

===

This implementation follows the approach outlined in Stephen Boyd's EE364a course (Convex Optimization).
See Homework 8 additional exercises: <https://see.stanford.edu/Course/EE364A>.
