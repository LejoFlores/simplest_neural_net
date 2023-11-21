# Simplest Hydrologic Neural Net

This repository provides a very basic introduction to building a neural network for hydrology from scratch. In these notebooks, a simple neural network to predict whether snow is observed on the ground at a Snotel site based on: (1) the mean air temperature for the day and (2) the day of year. This notebook is meant as a learning resource to understand how a neural network is built, trained, and tested. This is decidedly __not__ the way one would create a neural network for a more complicated problem, but is instead designed to provide a simple example to take a future machine learning afficionado "under the hood" of one of the most common machine learning approaches.

The neural net tries to predict a binary variable (snow on ground is either `True` or `False`) using predictor variables that are readily observed. We presume that the combination of day of year and mean air temperature are likely good predictors on whether or not snow is present. Day of year provides implicit information about season and is likely correlated with the presence/absence of snow (i.e., if I told you it was January 15 at a Snotel site, would you think snow is likely present? What about July 15?). Mean air temperature provides some information about the energy in the atmosphere and likely exhibits some correlation with the presence/absence of snow (i.e., if it is 26°C is it likely that snow is present? What about -15 °C?).

Note that this notebook very closely follows a nice example outlined in [this Medium article](https://towardsdatascience.com/machine-learning-for-beginners-an-introduction-to-neural-networks-d49f22d238f9) but uses real data from a Snotel site in an effort to make the problem more closely related to the hydrologic sciences. 

The network contains 2 input layers ('Day of Year' and 'Daily Mean Air Temperature'), 2 hidden layers (`h1` and `h2`), and a single output layer (`o1`, whether there is snow or not). Note that we're using the logistic sigmoid function as our activation function. So, the output of the neural network is a variable that is continuous on the interval (0,1). We turn this into a categorical variable by reclassifying output values between (0,0.5) as being _snow free_ and output values from [0.5,1.0) as being _snow covered_. The visualization of our neural network is as follows:

<img src='Neural Net Schematic.png' alt='Schematic of neural network' width='80%'/>

This repo contains the following 2 notebooks:
1. [1_DataCleanupStep.ipynb](./1_DataCleanupStep.ipynb): A data cleanup and processing step, and
2. [2_SimplestNeuralNet.ipynb](./2_SimplestNeuralNet.ipynb): A notebook in which we create, fit, and examine a neural net from scratch.
3. [3_SimplestNeuralNet_sklearn.ipynb](./3_SimplestNeuralNet_sklearn.ipynb): A notebook that repeats the previous example, but instead uses a machine learning library to fit the model. 