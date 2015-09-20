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

(This is just brainstorming, please sugggest!)

In all cases, we should explore a range of dimensional parameters.

Event 1
- Create an n x k array
- Apply a function over k
- Aggregate over n to yield a 1 x k array

Event 2
- Create an n x k array
- Apply a function over k
- Apply a function over n
- Aggregate over n to yield a 1 x k array

Event 3
- Burrows–Wheeler transform, based on this [example](http://mikolalysenko.github.io/ndarray-presentation/#/5/1)
- Generate all rotations of an 1 x k array (typically a string)
- Sort rows
- Select last column
 
Event 4
- Collection of n images each k x d
- Assign a random key to each image
- Average all images associated with each key
- Could do starting with images or time series
- Typical dimensions for @shoyer (and @freeman-lab!) are n=O(1000)-O(10000) and d,k=O(100)-O(1000)

Event 5
- SVD!

## Languages / Frameworks

Many of us do a lot of this kind of work in Python, but we might want to consider evaluating relative to Scala (especially in the multiple node setting), and in the local setting, I'm interested in playing with Julia, and I recently learned about a really cool Javascript [ndarray library](https://github.com/scijs/ndarray) that it'd be fun to play with.

- numpy (python)
- theano (python)
- dask.array (python)
- scijs-ndarray (javascript)
- torch (lua)
- spark (scala)
- spark (python)

