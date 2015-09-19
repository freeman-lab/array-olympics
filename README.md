# The Array Olympics!

## Overview

This repo is for collecting thoughts and ideas for benchmarking ndarray computations. We are less focused on the speed of core numerical computations (as have been covered elsewhere, e.g. [here](http://lessthanoptimal.github.io/Java-Matrix-Benchmark/) and [here](http://julialang.org/benchmarks/)), and more focused on how different ndarray abstractions perform across complex, real-world workflows -- involving applying multple functions / aggregations / reshapings of data over different dimensions -- especially in the context of distributed computing settings.

For now this repo can serve to collect notes on the **workflows** we want to consider, the **settings** in which we want to evaluate those workflows, and the **languages** we want to include. Moving forward, we can use this repo to collect implementations of the benchmarks, a CLI to run them, and a little website to show them.

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

## Workflows

(This is just brainstorming, please sugggest!)

In all cases, we should explore a range of dimensional parameters.

Example 1
- Create an n x k array
- Apply a function over k
- Aggregate over n to yield a 1 x k array

Example 2
- Create an n x k array
- Apply a function over k
- Apply a function over n
- Aggregate over n to yield a 1 x k array

## Languages / Frameworks

Many of us do a lot of this kind of work in Python, but we might want to consider evaluating relative to Scala (especially in the multiple node setting), and in the local setting, I'm interested in playing with Julia, and I recently learned about a really cool Javascript [ndarray library](https://github.com/scijs/ndarray) that it'd be fun to play with.

- numpy (python)
- theano (python)
- scijs-ndarray (javascript)
- torch (lua)
- spark (scala)
- spark (python)

