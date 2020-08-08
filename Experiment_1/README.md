# Experiment Description
This experiment studies the rate of convergence of the theoretical Markov chains underlying Bouncy Particle Sampler \(BPS\), Stochastic BPS \(SBPS\), ADMC Haario-Bardenet 
\(ADMC-HB\) and Hamiltonian MCMC \(HMC\) when we set the target distribution to be a 50-dimensional standard Normal distribution. At every 100th iteration of an MCMC, an empirical
normal distribution is estimated from the samples at that iteration. Then, we calculate the KL divergence between this empirical distribution and the target.

## Some experimental details
1. Because the target distribution is high-dimensional, for each MCMC, 601 chains are initialised so that the empirical distribution is calculated more accurately.
2. Google Colab is used in order to parallelise the execution of programs.

## Description of ipynb files
### [Basic_BPS_with_Gaussian](Github_Expt1_Basic_BPS_with_Gaussian.ipynb)
contains 2 functions and 1 defined class. The `BPS_basic` function is the algorithm for modelling the movement of the particle. The class `Gaussian` allows us to define 
Gaussian dist of arbitrary dimension, mean and covariance matrix. The `Gaussian` class is inputted into `BPS_basic` so that the particle moves in a Gaussian energy field.
`x_v_t_arbitrary_times` allows us to compute the particle's position and velocity at any time during its travel.

