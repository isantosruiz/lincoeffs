# lincoeffs
MATLAB code to extract the coefficients of symbolic linear equations.

LINCOEFFS - Coefficients of symbolic linear equations.
   This function extracts the coefficient matrix and the column vector
   containing the non-homogeneous terms of a system of linear equations.

## Syntax
> `[A,b] = LINCOEFFS(equations,variables)`
where "equations" is a column vector of symbolic equations
containing left and right sides separated by the == operator,
and "variables" is a column vector containing symbolic variables.
The output arguments, A and b, allow us to rewrite the equations
in the matrix form A*x=b.

## Examples
```matlab
syms m n
[A,b] = lincoeffs([3*m+10*n==0;m-n==4],[m,n])
rref([A,b])  % reduced row echelon form (Gauss-Jordan)

syms x [3,1]
equations = [5*x(1)-2*x(2)+x(3)==7
  x(1)+x(2)+x(3)==0
  2*x(1)+8*x(2)-x(3)==6];
[A,b] = lincoeffs(equations,x)
x = A\b   % solve the matrix equation
A*x == b  % test the solution
```

## Requires
   Symbolic Math Toolbox  

## License
```
===================================================================
The BeerWare License (Revision 69):
-------------------------------------------------------------------
<I. Santos-Ruiz> wrote this file. As long as you retain this notice
you can do whatever you want with this stuff.
If we meet some day, and you think this stuff is worth it,
you can buy me a beer in return.
===================================================================
```
