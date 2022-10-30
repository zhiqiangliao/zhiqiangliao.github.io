---
layout: post
title:  How to do normalization in MC simulations?
date:   2022-10-30 16:40:16
description: Statistics & Computer science
tags: code simulations
categories: math
---
Normalization usually helps accelarate convergence of algorithm.

<hr>

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/norm.png" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    Data splite process.
</div>

<hr>

The Python code is as follows:

{% highlight python linenos %}

    normalization = np.sqrt(np.sum(x**2, axis=0))/np.sqrt(x.shape[0])
    x = x/normalization

{% endhighlight %}