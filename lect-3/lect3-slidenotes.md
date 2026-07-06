# Introduction to Machine Learning

Extracting meaningful patterns from data -> automate a decision making process by generalizing from known examples. 

Supervised -> user provides the algorithm input / desired outputs -> algo finds a way to produce desired output given input

Unsupervised -> only input data is known, no known output data is given to algo. 

Reinforcement learning -> learning from interaction with an environment.

our class' learning process

Real world -> measuring devices -> preprocessing -> Dimensionality reduction -> model learning -> model testing -> analysis results. 

## Dimensionality in trading

incr in dimensionality -> exponential increase for amount of data needed for training and testing. 

Compression -> reducing redundant / correlated / noisy info

Feature extraction -> discover intrinsic structure

Visualization -> try to visualize?

Linear model; multiple responses, no predictors. 

Y = XB + e; Y is observed output, X is known matrix of predictors and B is unknown vector of parameters. Normal regression, both output and predictors are known.

PCA -> same model expression; output Y is matrix of several output columns, and parameters B have same number of columns as Y. Both multipliers X and B are unknown. 

PCA reduces dimensionality of output data by accurate description of correlation structure. 

Standardize d dimensional data; perform SVD to get all eigenvectors and eigenvalues; sort based on decreasing eigenvalues (larger EV = more variance captured on that eigenvector); pick k largest eigenvalues and eigenvectors, where k <= d and cum. explained variance is good enough; construct projection matrix W from k eigenvectors; transform original d dimensional dataset X using W to get k dimensional subspace Y. 

PCA: Component axes maximizing variance

LDA: maximizing component axes for class separation. 

LDA:

maximize scatter between classes, while minimizing scatter within class. 

(LDA = lineardiscriminantanalysis)

## Shrinkage

Reduce magnitude of model coefficients to prevent overfitting and improve generalizations.

Remove some parameters before fitting a model; based on technique constraining coefficient estimates. 

### Ridge regression

Minimize the sum of squares in fitting linear regression models. 

RSS -> Residual sum of squares. 

RSS (B; x, y) = \sum(y_i - f(x_i))^2, from i = 1 to N, which is then equal to \sum(y_i - B_0 - \sum(B_j x_ij))^2 from 1 to N (and second sum, from 1 to P). 

RSS finds coefficients B that minimize total squared prediction error on the training dataset; however this can lead to overfitting. 

Ridge Regression introduces a penalty to encourage coefficients to be clsoer to zero;

Ridge regresson => RSS + a(B), where a(B) = lambda \sum(B_J^2) from j = 1 to P. a(B) is the regularizator, and the lambda term is a tuning parameter. 

Minimizing both the shrinkage penalty (regulator) and the first term, the coefficient, forces coefficients to be smaller in absolute value.

Selecting an optimal lambda value is critical; different set of coefficient estimates for each value of lambda. 

Ridge reduction -> reduce variance of estimators; the bias variance tradeoff is as lambda increases, the flexibility of ridge regression fit decreases, leading to decreased variance but increased bias for coefficients. 

Regularization with L2-norm regularizator (sqrt of the regularizator). 

### Lasso regression -> 

shrink all coefficients towards zero, allow some coefficients to be equal to 0. The regularizator term is absolute value, not square. This removes weak keys. 


regularization in regression
- penalizing extra features in model. 
- Regular linear regression -> minimize SSE (RSS).
- Lasso -> minimize features that I am using.
- Introduce second term: penalty parameter, and coefficients of regression. 
- Consider error from fit + num features. 
- more features => lower SSE, but higher penalty.
- less features => higher SSE, lower penalty. 

## Decision Trees

Supervised: Can handle numerical and categorical data. 

Used as regression for prediction or classification model, handles multi output problems well.

robust to noise

easily interpretable (if-then, tree structure), can be visualized.

Classifies instances into one of a discrete set of possible categories: learned function is the whole tree; each node is a test on some attribute of the instance. Branches repr values of attributes. 

Problem types for DT:
- instances repr by attribute value pairs.

algo in book: attr have smaller num of discrete values

Can be extended to real valued attributes; target function has discrete output values. Can be extended. 

Robust.
- Classification errors
- errors in attribute values
- missing attribute values

Greedy search
- make decision making greatest improvement in what you are trying to optimize at each step
- No backtrack possible, unless dead end.
- not globally optimum, generally works well. 

"what attr best classifies training data at this point"

## Clustering

unsupervised: data unlabelled. 

Organizes into meaningful subgroups without prior knowledge of group membership.

k means euclidean distance based -> centroid based.
- pick sweet spot between SSE and number of clusters. 

## Clustering / SVM

max margin classifier -> formalize notion of the best linear separator

lagrangian multipliers -> convert constrained optimization problem to one that is easier to solve

kernels -> project data into higher dimensional space making it linearly separable. 

SVM -> effective in high dimensional spaces, never trapped in local minima, effective in cases where num dim > num samples. Uses subset of training points in decision function (SV), memory efficient. Versatile.
- Could overfit; does not provide probability estiamtes, calculated using five fold cross validation. Does not return importance of features. 

## Neural network

Pattern recognition -> other difficult-to-program tasks. 

Formed like human neurons: activation threshold + "next neuron"

Chooses to shoot out excitatory output based on activation threshold + excitatory input. 

Feed forward networks: Signals travel one way only. 

Feed forward NNs -> straightforward networks associating inputs with outputs. Also known as bottom up or top down. 

Input layer -> raw info fed into network 

Hidden layer (activity of iput units, weights on connections b/w hidden and input units)

Output layer -> behavior of output units, dependent on activity of hidden units. 

Network parameters -> weights initialized, num hidden layers + num neurons, examples in training set. 

back propogation: Adjust weights of NN to minimize network total MSE. 

## Standardizing data

transform each feature to have mean zero and STDEV 1. Ensure that features are measured with the same ruler. 

## PCA Analysis

Dimensionality reduction method: Takes a dataset with correlated variables and replaces them with fewer uncorrelated components explaining most of the variation. Projecting vectors onto lower dimensions. 