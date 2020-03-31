# Shifted Sphere Function

The function is coninuous and convex and has only one minumum value. So the best choise is to use a gradient based algorithm for optimization.
We use scipy optimizer with the Broyden-Fletcher-Goldfarb-Shanno algorithm with default paramters.
The algorithm should be able to estimate the gradient itself.

Minimum is found pretty quikly already on the 3rd - 4th iteration. Computational time is very low.
