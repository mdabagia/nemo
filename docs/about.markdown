---
layout: page
title: About
permalink: /about/
---
## Motivation

NEMO is intended to capture a few desirable qualities for a model of the brain, especially from the perspective of computer science:

* It is minimal, in the sense that its core assumptions arise from widely-accepted ideas about what the brain does;
* It is abstract, enough to analyzed and simulated efficiently;
* It is a model of computation, and so can be analyzed using the tools of theoretical computer science;
* It is not hand-built to solve a particular task, and is instead meant to reflect the apparently homogeneous and general-purpose neural hardware  that prevails in the mammalian cortex;
* In particular, it learns from its environment, using mechanisms that are thought to be biologically implementable.

## Model Description

In brief, NEMO is a dynamical system which is parameterized by a set of interconnected *brain regions*. Each brain region is a set of *neurons*. Synaptic connectivity is positively weighted and directed (if neuron a stimulates neuron b, b doesn't necessarily stimulate a) and determined randomly; if a pair of brain regions is connected, then each of their neurons has a connection with some (small) probability, independently of all the others. Regions may also be recurrently connected, similarly randomly. The dynamics proceed in discrete time, and at each timestep every neuron is either "firing" or not. Neurons determine their activation by summing up all of their incoming weights from neighbors which fired on the previous timestep, and the neurons which actually fire are determined on a region-by-region basis as the *k* with the largest activations. This *k*-winners-take-all process abstracts inhibition, by which a population of inhibitory neurons regulates the firing of their excitatory neighbors.

Finally, weights in the model may be updated according to Hebbian plasticity: For a synapse from neuron *i* to neuron *j*, each time *i* fires followed by *j* on the next time step, the synaptic weight is strengthened. 

[comment]: It arose out of the "Assembly Calculus", a model which had very similar aims but relied on external control rather than well-defined internal mechanisms to coordinate firing and implement more involved computations. The core papers of the project are:

