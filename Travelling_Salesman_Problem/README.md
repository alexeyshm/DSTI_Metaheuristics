# Travelling Salesman Problem

The goal is to find the shortest path to visit all cities without visiting the same one twice.

Two datasets from http://www.math.uwaterloo.ca/tsp/world/countries.html are used:
- Djibouti (38 cities)
- Qatar(194 cities)

The coordinates are converted to csv format.

For solving a discrete problem we chose a suitable heuristic algorythm, in particular simulated annealing. 
It combies inital randomness with more targeted search of the local optimums for later stages. That should provide a good trade-off between finding an appropriate solution and reducing computational comlexity of TSP.

We use simanneal algorythm for Python, which has a class to deal with TSP functions.
The package https://github.com/perrygeo/simanneal should be installed to be able to reproduce the solution.

Some modifications have been made to the available code:
 - adoptation to process data from Pandas dataframes.
 - saving preliminary statistics during the computation into a table.
 - printing the computation time and visualisation of the solution
 
 The algorythm uses three parameters, which can be optimized:
 - Tmax - start temperature
 - Tmin - minumum temperture 
 - steps - number of iterations
 
 The strategy to tune the algorytm is following:
 - start with excessively high values of Tmax and steps, and small value of Tmin, which should get us an optimal result at a cost of computational time. The "tail" of the convergence curve will be quite long at this case.
 - select Tmax, such that the acceptance rate would be higher than 98%
 - select smalles Tmin and number of iterations, s.t. the distance starts to converge to the mimimum.
 
The final model we chose reaches the most optimal solution for this algorythm, while trying to keep computational time as low as possible, by using number of iterations and Tmin farthest possible along the convergence curve.

However, in cases, where the distance doesn't need to be strictly mimimal, the computational time can be improved significantly at costs of a few percent of the distance value. This is especially valid for cases with more points.

