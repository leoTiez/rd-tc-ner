# Estimating a Reaction-Diffusion System
Whilst the dynamics in systems can be defined neatly using differential
equations, the approximation of their parameters becomes quickly
intractable when dealing with PDEs. Reaction-Diffusion systems offer a potent
toolset to analyse a set of non-linear PDEs. Here, we make use of a modified
version of an expected maximisation (EM) algorithm using BSplines, which 
was proposed by Brewer et al. 2008 [1], to derive the parameters of a 
reaction-diffusion system from data points.
A more detailed description is soon to come.

## Requirements
Please install the following software 
- Python3
- pip3
- singularity (if you want to run the model in a virtual environment)

## Installation of Python libraries
To install the necessary python requirements simply run
```bash
python3 -m pip install -r requirements.txt
```

## Run the test case
Run 
```bash
python3 test_main.py
```

It will load the dummy data from the data directory
and try to derive the correct parameters for the ODE.
Note that the algorithm is heavily dependent on
the degree that is used for the BSplines to approximate
the time course. While a degree of `k=5` or `k=4` should produce
an outcome like

![Solution for k=4 or k=5](figures/test_k5.png)

setting the degree of the BSplines to `k=3` has a large
influence on the derived parameters and hence on the
system dynamics

![Solution for k=3](figures/test_k3.png) 

## References
[1] Brewer, Daniel, et al. "Fitting ordinary differential equations to short time course data." Philosophical Transactions of the Royal Society A: Mathematical, Physical and Engineering Sciences 366.1865 (2008): 519-544.