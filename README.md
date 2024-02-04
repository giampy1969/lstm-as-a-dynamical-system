# LSTM as a dynamical system

[![View LSTM as a Dynamical System on File Exchange](https://www.mathworks.com/matlabcentral/images/matlab-file-exchange.svg)](https://www.mathworks.com/matlabcentral/fileexchange/124970-lstm-as-a-dynamical-system)

[![Open in MATLAB Online](https://www.mathworks.com/images/responsive/global/open-in-matlab-online.svg)](https://matlab.mathworks.com/open/github/v1?repo=giampy1969/lstm-as-a-dynamical-system)

This example explains how an LSTM (Long Short-Term Memory) layer can be seen as a nonlinear dynamical system with a specific structure, and sheds some light on whether, and how, an LSTM layer can approximate a linear dynamical system. 

In the first part of the example, a network containing a single LSTM layer is defined and simulated using both the Deep Learning Toolbox&trade; and Simulink&reg;. The Simulink representation, being more visual, clearly shows the two underlying feedback loops at the heart of the LSTM layer. The fact that the number of parameters of an LSTM scales quadratically with the number of units is also highlighted and explained here.

The second part of the example asks (and answers) the question of how well an LSTM layer can approximate a dynamical system. 

Here, given a simple discete-time linear dynamical system in which the A matrix is invertible, a set of LSTM weights is first calculated directly from the true matrices of the system. With such weights, the LSTM network reproduces the behavior of the original linear system to any desired accuracy. This fact is explained in theory and illustated in practice.

A natural question is then what happens when the network is trained starting directly from the calculated weights. The related analysis shows that the calculated solution lies in a very narrow attraction basin, from which the training algorithm can very easily get out even with relatively small learning rates.

The final, and most important, question is whether, when starting from random initial weights, the training algorithm can find a solution that is close enough to the one calculated from the true system matrices. 

The answer seems to be negative: the training algorithm ends up in a local minimum that is very dependent on both the initial conditions and the hyperparameters. This solution is also quite different from (and does not perform as well as) the solution previously calculated from the system matrices.

Note that this example is meant to illustrate the stucture of an LSTM and some of its theoratical capabilities and limitations. If you want to quickly build and train an LSTM in MATLAB&reg; see [LSTM Networks](https://www.mathworks.com/help/deeplearning/ug/long-short-term-memory-networks.html). Also, for a complementary example that uses a network with two LSTM layers with several thousands of parameters for system identification, see [Use LSTM Network for Linear System Identification](https://www.mathworks.com/help/ident/ug/use-lstm-for-linear-system-identification.html).


## Getting started

Open LSTM_explained.mlx in MATLAB (version R2023a and above) and follow from there. Running the file section by section is suggested.

# Requirements

MATLAB
Deep Learning Toolbox

Note: The initial part of the example uses Simulink, but you can follow and execute through most of the example also without it.

# Content

1) LSTM_explained.mlx -  Main file
2) lstm_sim.mdl      -  Simulink model of an LSTM layer 

## Author
Giampiero Campa - April 2023
