# ACADO Toolkit [![Build Status](https://travis-ci.org/acado/acado.png?branch=stable, master)](https://travis-ci.org/acado/acado) [![Build status](https://ci.appveyor.com/api/projects/status/fai4cc4kavjv4nq8)](https://ci.appveyor.com/project/mvukov/acado)

> Toolkit for Automatic Control and Dynamic Optimization

ACADO Toolkit is a software environment and algorithm collection for automatic control and dynamic optimization. It provides a general framework for using a great variety of algorithms for direct optimal control, including model predictive control, state and parameter estimation and robust optimization. ACADO Toolkit is implemented as self-contained C++ code and comes along with user-friendly MATLAB interface. The object-oriented design allows for convenient coupling of existing optimization packages and for extending it with user-written optimization routines.

More information about the toolkit can be found at the [homepage](http://www.acadotoolkit.org).

------------------------------------------------------------------------------------------------------------------------------------------
I have already implemented an example of the model predictive control for an automated car with nonlinear dynamics in a very simple scene to track a straight road and meanwhile a steady speed starting from a point outside of the lane. At the start point, $u_x = 10$, $u_y = 0$, $X =0$, $Y=10$, $\psi = pi/2-0.001$. The tracking road is $Y=5$, the target speed is $u_x = 12$. The simuliation time $T=5s$.

I firstly realized it in MATLAB and solved the finital horizontal optimal control problem by the nonlinear constraint problem solver fmincon with interior point method. It took about 23s seconds to simulate the wohle process, almost 5 times over the real time simulated, which was not acceptable. The first simution step took about 800ms. So I tried to find a high performance solver to overcome the low simulation speed. At last, I did the same experiment in ACADO tookit. It also took 700ms-800ms in one simulation step. I felt very depressed.

