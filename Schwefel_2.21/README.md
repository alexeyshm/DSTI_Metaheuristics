## Metaheuristics
### Schwefel's Problem 2.21

The function is not smooth, second-order derivative will be 0.
It restricts selection of optimization algprithms we could apply.
Usage of scimplex algorythm doesn't bring satysfactory results.

The chosen algorithm is BFGS, using first-order derivatives. 
Empirically, it converges to the lowest value of the function in compare with other applicable methods (e.g. Nelder-Mead, Powell, CG). 
'gtol' parameter is etimated at 1e-3, as the algorith teminates successfully in different dimentions and the result is more consistent. 
