Embedded Conic Solver (ECOS)
====

ECOS is a numerical software for solving convex second-order cone programs (SOCPs) of type
```
min  c'*x 
s.t. A*x = b
     G*x <=_K h
```
where the last inequality is generalized, i.e. `h - G*x` belongs to the cone `K`. 
ECOS supports the positive orthant `R_+` and second-order cones `Q_n` defined as
```
Q_n = { (t,x) | t >= || x ||_2 } 
```
In the definition above, t is a scalar and `x` is in `R_{n-1}`. The cone `K` is therefore
a direct product of the positive orthant and second-order cones:
```
K = R_+ x Q_n1 x ... x Q_nN
```

Features of ECOS
----
 
+ *ECOS runs on embedded platforms*. Written in ANSI C, 
  it can be compiled for any platform for which a C compiler is available. Excluding the problem setup
  part, no memory manager is needed for solving problem instances of same structure. 
+ *ECOS is efficient*. Using sparse linear algebra routines, it computes only what is really necessary.
  The interior point algorithm it implements is one of the fastest converging methods that are currently
  in use for solving convex conic problems.
+ *ECOS has a tiny footprint*. The ECOS solver consists of 750 lines of C code (excluding the problem setup 
   code).
+ *ECOS is numerically robust*. Using regularization and iterative refinement coupled with a carefully chosen 
  sparse representation of scaling matrices, millions of problem instances are solved reliably.
+ *ECOS comes with a MATLAB and CVX 2.0 interface*. This way, you can prototype, simulate and verify the performance
  of ECOS before you implement the very same code on your embedded hardware.
