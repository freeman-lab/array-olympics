# The Array Olympics!

## Overview

This repo is for collecting thoughts and ideas for benchmarking ndarray computations. We are less focused on the speed of core numerical computations (as have been covered elsewhere, e.g. [here](http://lessthanoptimal.github.io/Java-Matrix-Benchmark/) and [here](http://julialang.org/benchmarks/)), and more focused on how different ndarray abstractions perform across complex, real-world workflows -- involving applying multple functions / aggregations / reshapings of data over different dimensions -- especially in the context of distributed computing settings.

For now this repo can serve to collect notes on the **events** we want to consider, the **settings** in which we want to evaluate those events, and the **languages** we want to include. Moving forward, we can use this repo to collect implementations of the benchmarks, a CLI to run them, and a little website to show them.

## Settings

(Note that some of these settings will only apply to some of the languages / frameworks)

Single node
- 1 core
- 8 cores
- GPU

Multiple nodes
- 5 nodes 
- 10 nodes 
- 20 nodes 

## Events

Suggested events include:

1. Aggegation 
2. Mapped function + aggregation
3. Burrows–Wheeler transform
4. Aggregate images by key
5. SVD (including out-of-core)

Detailed descriptions are available in the [wiki](https://github.com/freeman-lab/array-olympics/wiki)

## Languages / Frameworks

Many of us do a lot of this kind of work in Python, but for the Spark setting we should consider evaluating relative to Scala, and in the local setting it would be interesting to compare to other languages (including Julia and Javascript).

Note that all languages are appropriate to the "single node + 1 core" setting, but only some are relavant to other settings (e.g. only Spark for the multiple node settings, only torch and theano for GPUs, etc.)

- numpy (python)
- theano (python)
- dask.array (python)
- scijs-ndarray (javascript)
- torch (lua)
- spark (scala)
- spark (python)

