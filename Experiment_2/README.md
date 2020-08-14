# Experiment Description
In this folder, a new algorithm for simulating Stochastic BPS is implemented in Python. Then, a number of tests have been carried out in order to discover 
underlying errors \(which have all been corrected\) and to assess the performance of the algorithm.

## Description of ipynb files
### [SBPS_new_implementation](Github_SBPS_new_implementation.ipynb)
The function `SBPS` is the MCMC algorithm for sampling from a target distribution. Its arguments are: `x0`, `v0`, `Time`, `lambda_ref`, `prob_dist`, `num_lin_reg`, 
`k`, `d_geom`. The special/specific parameters are `num_lin_reg`, `k`, `d_geom`:
1. `d_geom` represents the distance in the parameter space/sample space ahead of the particle on which an upper-bound intensity function is created for performing
adaptive thinning.
2. `k` is a parameter that controls how large the intensity function is.
3. `num_lin_reg` represents the number of points we sample from the distance `d_geom` ahead to perform Bayesian Linear Regression, which in turn produces a proposed 
upper-bound intensity function.

### [Testing SBPS on Noisy Gaussian Distribution](Github_Test_new_SBPS_on_Gaussian.ipynb)
The codes in this file concerns the running of `SBPS` on the 2-dimensional standard Gaussian distribution. Some particle's trajectories are plotted. Moreover, histograms
of MCMC samples in 0-20000th iteration are plotted; and comparisons between empirical probabilities and theoretical probabilities are calculated.

### [New Adapative Thinning algorithm: Analytic Bisection](Github_test_analytic_bisection_algor.ipynb)
`SBPS` utilises a function called `analytic_Bi_adaptive_thinning`, which allows it to simulate the arrival of bounce events through adaptive thinning. In short, this algorithm
utilises the bisection method and a large number of analytic computation with an aim to speed up the simulation. Another algorithm that linearly interpolates the upper-bound intensity for simulation was proposed before. The code in this file uses 3 different upper-bound intensity functions to test whether the 2 algorithms are outputting the same (or very close) arrival time of events, in order to see whether `analytic_Bi_adaptive_thinning` contains errors. Moreover, the computational speed of the 2 algorithms have been 
measured, in order to see how much the employment of bisection method and analytic computations increases the computational speed.
