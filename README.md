# Venture-Capital-Neural-Network-Classifier

This application attempts to use a neural network analysis to predict the whether venture capital investments will successful. A sample dataset was provided for analysis.

First the data will be prepared for analysis. Then several models of neural networks will be run on the data to see what rate of successful prediction can be achieved. The accuracies of the various models will be displayed and compared. The neural network models will be saved in HDF5 format.

## Technologies

This program was written in Python 3.7 and can be run in Jupyter Lab.

The following libraries are used:

- pandas
- numpy
- sklearn
- tensorflow and keras

## Installation Guide

You will need to verify that you have installed the libraries listed in the Technologies section.

## Usage

The application `venture_funding_with_deep_learning.ipynb` can be run in Jupyter Lab. 

## Contributors
This program was written by Preston Hodsman based on a request for analysis from Trilogy Education Services, a 2U, Inc.

## License
MIT

# Report

The first attempt at a neural network used two layers of neurons and the adam optimization function. It achieved an accuracy of 73 percent on the test data.

Four additional attempts were made:

- The first alternative model is identical to the first one, except with some different preprocessing of the data. Two columns which have all the same value are removed. The column of the income amount of the organization is changed from a range to the value at the upper end of that range. The income amount and ask amounts are first scaled with a natural log function before StandardScaler is applied.

- The second alternative model uses the same alternative preprocessing and neural network structure as the first, but uses the Nadam optimization function.

- The third alternative model uses the same alternative preprocessing, the Nadam optimization function, but uses four layers of neurons.

- The fourth alternative model attempts to see if a higher rate of accuracy can be achieved with only considering data for funding ask amounts of under 200 thousand dollars. It uses the same preprocessing as the other alternative models, the Nadam optimization function, two layers of neurons, but an increased amount of epochs.

![](https://raw.githubusercontent.com/phodsman/Venture-Capital-Neural-Network-Classifier/main/Screenshot%202021-12-16%20103653.png)

The end result is there is very little difference between these different models. All have accuracies of about 73 percent when run on the split test data. There is only a modest increase of maybe 1 percent to 74 percent for a model being run only on funding requests for under 200 thousand dollars. 

From this we can see that for this particular set of data:

- Changing the optimization function to Nadam from adam did not make a significant difference.

- Removing irrelevant columns did not make a significant difference

- Changing ranges to representative values did not make a significant difference

- Doing natural log functions to scale the values before applying StandardScaler did not make a significant difference.

The sample data has about a 53 percent success rate, so there was no need for an imbalanced learn specific algorithm. It is not specified how much of the investments from unsuccessful ventures was recovered, or how much additional income was received from successful venture funding, so the increase in returns from a 73 percent success rate in a neural network identification is not computable on this data set.