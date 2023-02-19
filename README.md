# LSTM as a dynamical system

[![View LSTM as a Dynamical System on File Exchange](https://www.mathworks.com/matlabcentral/images/matlab-file-exchange.svg)](https://www.mathworks.com/matlabcentral/fileexchange/124970-lstm-as-a-dynamical-system)

This example explains how an LSTM (Long Short-Term Memory) layer can be seen as a nonlinear dynamical system with a specific structure, and sheds some light on whether, and how, an LSTM layer can approximate a linear dynamical system. 

In the first part of the example, a network containing a single LSTM layer is defined and simulated using both the Deep Learning Toolbox&trade; and Simulink&reg;. The Simulink representation, being more visual, clearly shows the two underlying feedback loops at the heart of the LSTM layer. The fact that the number of parameters of an LSTM scales quadratically with the number of units is also highlighted and explained here.

The second part of the example asks (and answers) the question of how well an LSTM layer can approximate a dynamical system. 

Here, given a simple linear dynamical system, a set of LSTM weights is first calculated directly from the true A, B, and C matrices of the system. The fact that the LSTM, due to the structure of its output equation, has to trade-off between approximating the state-dependent (C matrix) and input-dependent (D matrix) paths is also explained in some depth. Nevertheless, using the calculated weights, the resulting approximation is quite good.

A natural question is then whether the training algorithm, when started directly from the calculated weights, can improve upon this solution. The related analysis shows that, while the answer can sometime be positive (provided that a small learning rate and a large number of epochs is used), the solution lies in a very narrow attractor, from which the training algorithm can very easily get out.

The final, and most important, question is whether, when starting from random initial weights, the training algorithm can find a solution that is close enough to (or possibly better than) the one calculated from the true system matrices. 

The answer seems to be negative: the training algorithm ends up in a local minimum that is extremely dependent on both the initial conditions and the hyperparameters. This solution is also quite different from (and does not perform as well as) the solution previously calculated from the system matrices.

Note that this example is meant to illustrate the stucture of an LSTM and some of its theoratical capabilities and limitations. If you want to quickly build and train an LSTM in MATLAB&reg; see [LSTM Networks](https://www.mathworks.com/help/deeplearning/ug/long-short-term-memory-networks.html). Also, for a complementary example that uses a network with two LSTM layers with several thousands of parameters for system identification, see [Use LSTM Network for Linear System Identification](https://www.mathworks.com/help/ident/ug/use-lstm-for-linear-system-identification.html).


## Getting started

Open LSTMexplained.mlx in MATLAB (version R2022b and above) and follow from there. Running the file section by section is suggested.

# Requirements

MATLAB
Deep Learning Toolbox

Note: The initial part of the example uses Simulink, but you can follow and execute through most of the example also without it.

# Content

1) LSTMexplained.mlx -  Main file
2) lstm_sim.mdl      -  Simulink model of an LSTM layer 

## Author
Giampiero Campa - December 2022
