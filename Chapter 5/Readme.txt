### Instructions for Rand.init 

This function is used to initialized all the algorithms.

X = a dataset with array structure of dimension [p,r,n], with p = rows, r = columns, n = units; if n = 1, insert a matrix of dimension p x r.
k = number of mixture components;
density = one of "norm", "sen", "tin" or "t";
init.sec = a matrix with nstarR rows and k columns that indicate which random observations of X select for starting the short-EMs. Should be used if the same initialization for the common parameters of all the models is desidered.
nstartR = the number of short-EMs to compute; 
nstartG = indicate the number of parameter sets that must be returned as output, according to the top nstartG log-likelihoods values;
nThreads = number of cores for parallel computing; note that this value must be equal to or lower than the value in the nstartG argument.

### Instructions for Mix_Nor_MV / Mix_T_MV / Mix_Sen_MV / Mix_Tin_MV

These functions are used to run the EM-based algorithms for each model.

X = a dataset with array structure of dimension [p,r,n], with p = rows, r = columns, n = units;
k = number of mixture components;
init.par = initial parameter sets obtained from the Rand.init function;
nstartG = indicate the number of complete EM-based algorithm that must be executed; note that this value must be equal to or lower than the value in the nstartG argument of the Rand.init function;
nThreads = number of cores for parallel computing; note that this value must be equal to or lower than the value in the nstartG argument;
tol = convergence thresold of the algorithm;
Mstep = one of "AECM" and "ECME";
method = optimization algorithm for the "ECME" option.

### Instructions for rsenMV and rtinMV

These functions are used to generate data from a matrix-variate SEN or TIN.

n = number of observations;
M = a mean matrix of dimension p x r;
U = a row covariance matrix of dimension p x p;
V = a column covariance matrix of dimension r x r;
theta = the tail-heaviness parameter.

### Instructions for Rand.mixt

This funcion can be used to generate data from a mixture of k matrix-variate distributions.

n = number of observations;
k = number of mixture components;
M = an array of dimension [p,r,k] for the means;
U = an array of dimension [p,p,k] for the row covariance matrices;
V = an array of dimension [r,r,k] for the column covariance matrices;
theta = a vector of dimension k for the tail-heaviness parameters;
prob = a vector of dimension k for the mixture weights;
density = one of "norm", "sen", "tin" or "t".

### Instructions for kurt and w.kurt

These functions are used to compute the kurtosis of the models and the weighted kurtosis of a sample.

p = number of rows of each data matrix;
r = number of columns of each data matrix;
theta = the tail-heaviness parameter;
density = one of "norm", "sen", "tin" or "t";
X = a matrix containing the vectorized version of the data. It has n rows, and p*r columns;
w = a vector of n weights.


