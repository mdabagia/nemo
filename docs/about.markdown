---
layout: page
title: About
permalink: /about/
---
## Motivation

![Principles of Neural Science, Sixth Edition, Kandel et al.](https://www.mhprofessional.com/media/catalog/product/cache/081b8c22b4dd107671c14f517fd777a1/9/7/9781259642234_233.jpeg)

The reference text for every neuroscientist is the monolithic *Principles of Neural Science*, which is a towering 1700 pages in its sixth edition. We are optimistic that its title is mistaken; we hope that the true principles by which intelligent behavior arises from the brain, the central object of study of neuroscience, can be laid out far more simply. For this to be true, it must be that much of the valuable information that experimentalists have uncovered about how the brain works is mere "implementation detail" from the perspective of cognition. 

As computer scientists, we are interested in thinking about the brain as a model of computation. This entails making some hypotheses about what operations the "details" of neural anatomy and dynamics implement, defining a model based on these hypotheses, and then exploring the sorts of algorithms that this model can efficiently realize. Results in this direction have two flavors: "positive" results assert that the model can do some interesting task, which is evidence that it is a good model of cognition; "negative" results, on the other hand, show that it is difficult for the model to perform some task, which can be used to re-evaluate the hypotheses used to define the model or as additional evidence that it is a good model when the task is also known to be difficult for the brain. 

NEMO is intended to capture a few desirable qualities for a model of the brain, especially from the perspective of computer science:

* It is minimal, in the sense that its core assumptions arise from widely-accepted ideas about what the brain does;
* It is abstract, enough to analyzed and simulated efficiently;
* It is a model of computation, and so can be analyzed using the tools of theoretical computer science;
* It is not hand-built to solve a particular task, and is instead meant to reflect the apparently homogeneous and general-purpose neural hardware  that prevails in the mammalian cortex;
* In particular, it learns from its environment, using mechanisms that are thought to be biologically implementable.

Philosophically, NEMO takes an approach to studying the brain drawn from theoretical computer science: 

## Model Description

In brief, NEMO is a dynamical system which is parameterized by a set of interconnected *brain areas*. Each brain area is a set of *neurons*. Synaptic connectivity is positively weighted and directed (if neuron a stimulates neuron b, b doesn't necessarily stimulate a) and determined randomly; if a pair of brain areas is connected, then each of their neurons has a connection with some (small) probability, independently of all the others. areas may also be recurrently connected, similarly randomly. Input to the model arises in designated "input" areas, which may have their activity set externally to the dynamics that drive the rest of the model.

The dynamics proceed in discrete time, and at each timestep every neuron is either "firing" or not. Neurons determine their activation by summing up all of their incoming weights from neighbors which fired on the previous timestep, and the neurons which actually fire are determined on a area-by-area basis as the *k* with the largest activations. This *k*-winners-take-all process abstracts inhibition, by which a population of inhibitory neurons regulates the firing of their excitatory neighbors.Finally, weights in the model may be updated according to Hebbian plasticity: For a synapse from neuron *i* to neuron *j*, each time *i* fires followed by *j* on the next time step, the synaptic weight is strengthened. Lastly, areas can be entirely inhibited, so that no neurons within them fire on a given timestep. We generally consider this to occur periodically, independently of which specific neurons are firing, which is meant to abstract the brain's rhythmic activity.

When choosing an instance of the model for a specific task, the choices available to the designer are the number, connectivity, and inhibition schedule of brain areas, as well as where and when the input will be presented.

[comment]: It arose out of the "Assembly Calculus", a model which had very similar aims but relied on external control rather than well-defined internal mechanisms to coordinate firing and implement more involved computations. The core papers of the project are:

