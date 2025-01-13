---
layout: page
title: Assemblies of Neurons
permalink: /assemblies/
---

Assemblies are groups of neurons whose coordinated firing is hypothesized to be the basic unit of cognition, representing objects, memories, and other relevant concepts. The first discovery that sparked interest in NEMO was that assemblies rapidly form within a brain region in response to repeated stimulation by a fixed input, and are recalled later when the same input appears again.

The precise setup in which results have been proven is the following: There are two areas, one which provides input to the other. In the input area, there is a designated set of stimulus neurons of size *k*. This set fires repeatedly, on every time step, indefinitely, and evokes a response in the other area.

![The setup for assembly formation](https://raw.githubusercontent.com/mdabagia/nemo/master/docs/assets/images/assembly_formation.png){:style="display:block; margin-left:auto; margin-right:auto"}

What can be shown in theory and experiment is that, as long as the effect of Hebbian plasticity is sufficiently strong, the firing set quickly converges to a single set of neurons of size *k* which fires on every timestep [1]. Moreover, in the future, when the stimulus neurons fire again, the set which fires in response will immediately be the converged set from before. On this basis, we call the converged set an *assembly* which corresponds to the stimulus.

![An animation of assembly formation](https://raw.githubusercontent.com/mdabagia/nemo/master/docs/assets/images/assembly_formation.gif){:style="display:block; margin-left:auto; margin-right:auto"}

Further results relax the requirement that the exact same stimulus fires on every time step; as long as the stimuli on different time steps are sufficiently similar (in the sense that the overlap of their firing neurons is high) convergence still occurs and the assembly will be recalled for similar simuli [2]. This allows NEMO to naturally learn and implement a linear classifier.

References:
1. [Christos Papadimitriou & Santosh Vempala: "Random Projection in the Brain and Computation with Assemblies of Neurons." 10th Innovations in Theoretical Computer Science (2019).](https://par.nsf.gov/servlets/purl/10094284)
1. [Max Dabagia, Christos Papadimitriou, & Santosh Vempala: "Assemblies of neurons learn to classify well-separated distributions." Conference on Learning Theory, PMLR (2022).](https://proceedings.mlr.press/v178/dabagia22a.html)



