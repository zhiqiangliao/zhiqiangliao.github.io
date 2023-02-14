---
layout: post
title:  Standardization in Machine Learning
date:   2022-10-30 16:40:16
description: Statistics & Machine learning
tags: math code # math, github, code, essay (in yml file)
categories: Research
comments: true
---
Normalization usually helps accelarate convergence of algorithm.

## 0-1 standardization (MinMaxScaler)

MinMaxScaler standardization is one of the most widely recognized approaches to standardize information. For the variables, the base estimation of that element gets changed into 0, the most extreme worth gets changed into a  1, and each other worth gets changed into a decimal somewhere in the range of 0 and 1. For the responses, the elements can be standardized to have unit $$\|\cdot\|_2$$ norm. In many applications, the responses $$y$$ also retain the original scales.

{% highlight python %}
# Python code
import numpy as np
from sklearn import preprocessing

scaler = preprocessing.MinMaxScaler()
x = scaler.fit_transform(x)
y = y/np.linalg.norm(y)

{% endhighlight %}

{% highlight julia %}
# Julia code
using StatsBase
scaler = fit(UnitRangeTransform, x, dims=1)
x = StatsBase.transform(scaler, x)
y = y ./ norm(y)

{% endhighlight %}

## Z-score standardization (StandardScaler)

The StandardScaler is used for standardizing scores on the same scale where the variables are standardized to have unit $$\|\cdot\|_2$$ norm.

{% highlight python %}

# Python code
import numpy as np
x = (x - np.mean(x, axis=0))/np.linalg.norm(x, axis=0)
y = y/np.linalg.norm(y)

{% endhighlight %}

{% highlight julia %}
# Julia code
using StatsBase
scaler = fit(ZScoreTransform, x, dims=1)
x = StatsBase.transform(scaler, x)
y = y ./ norm(y)

{% endhighlight %}