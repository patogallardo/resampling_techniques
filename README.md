# Resampling

One popular way of inferring spread on an estimated quantity from a dataset is to use resampling.

Lets suppose one wants to compute an estimated quantity from data f(x1, x2, ...). What is the spread in the distribution of f?

## The Bootstrap

The bootstrap is a prescription for estimating the error in f. It consists of randomly drawing replicant samples from an observed distribution. 
The replicant samples need to be drawn with resampling. The idea here is that by repeating the observed samples, one is resembling the true underlying distribution generating the dataset.

After replicant samples are drawn, one can compute percentiles and intervals of confidence.

## The Jackknife

The Jackknife is another way of computing the standard error. Historically the jackknife arose as a faster way of computing a boostrapped error. The simplest variant of the jackknife is the delete-1 jackknife, where one sample is deleted from the sample and the estimator is compututed for the rest of samples.
If the estimator is an average, then the partial sum can be carried over and deleting one sample is equivalent to sustracting that number from the carried over sum.

Other variants of the jackknife exist: delete-d jackknife or group-g jackknife to name a few.

When computing a jackknife, the standard error has to be inflated by a factor that depends on the number of jackknife iterations. This factor arises from the fact that the replicant samples are dependent from the parent sample, so the estimated value is quite close to the full sample estimated value.

Another thing to consider is that the jackknife is more restrictive than the bootstrap in the sense that there are more families of estimators that fail the jackknife but still work while bootstrapping. The median is one classical example of this.

[Bootstrapping error in the median](https://github.com/patogallardo/resampling_techniques/blob/master/Uncertainty%20in%20the%20median.ipynb)
