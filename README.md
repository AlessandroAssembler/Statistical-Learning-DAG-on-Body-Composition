# DAG-Selection-Hill Climbing Method-Gaussian Bayesian Network-Estimation-BodyFat
This paper is based on the example analysis contained in Chapter 8 of Scutari's book on Bayesian Networks "Bayesian Networks with Examples in R" [1]. 
The author uses a dataset similar to the one chosen for this analysis to:

- select an optimal DAG (Directed Acyclic Graph) by imposing partial topological ordering;

- make predictions about the obtained GBN (Gaussian Bayesian Network). 

The objective is to estimate the relationships between 9 response variables Y (fat part and lean part of different body parts) and 5 explanatory variables X (age, height, weight, abdominal circumference, BMI).

The main steps followed by the author include:

- Dividing the dataset into training set and test set.

- Fitting a full (saturated) multivariate model including all variables.

- Searching for an "optimal" DAG model using a Score based Greedy (Hill Climbing) search algorithm. Specifically, a topological structure is specified using whitelists (blacklists) with the BNlearn package. It is imposed that variables Y are never parents of variables X. 

- Parameter estimation assuming a multivariate Gaussian distribution for the Bayesian network.

- Graphical representation of the obtained model.

The criterion used for selection by Hill Climbing is the BIC (Bayesian Information Criterion), while the SEP (Standard Error of Prediction), calculated as the square root of the sum of the square of the bias and the square of the standard deviation, is taken into account to evaluate the goodness of the model.

# Dataset

The dataset chosen is "BodyFat.csv," which contains anatomical data from a sample of 252 men of different ages. The objective is to estimate two response variables: BodyFat (body fat) and Wkg (weight in kilograms), using 12 explanatory variables, including age, height, and circumferences of different body parts (neck, waist, chest, wrist, biceps, thigh, etc.).
