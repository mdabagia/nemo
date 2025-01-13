---
layout: page
title: Sequences of Assemblies
permalink: /sequences/
---

Many types of stimuli the brain encounters possess temporal structure, or sequentiality. Navigation involves a sequence of landmarks, planning consists of generating a sequence of actions, and language is nothing but sequences of tokens. If assemblies are the most basic unit of cognition, then sequences should be a natural higher-level structure to combine them into.

Sequences of assemblies arise quite naturally in NEMO. The simplest setup is much like that for assembly formation, with an input area and a main area. A sequence of stimuli fires in the input area -- crucially, a *different* stimulus fires on each time step. This evokes a sequence of responses in the main area.

![The setup for forming a sequence of assemblies](https://raw.githubusercontent.com/mdabagia/nemo/master/docs/assets/images/simple_seq.png){:style="display:block; margin-left:auto; margin-right:auto"}

As long as the individual stimuli are sufficiently dissimilar from each other, their corresponding responses will be dissimilar from each other as well. And as long as the plasticity is not too strong, this sequence of responses will be exactly the same, each time the stimuli sequence is presented. Thus, after seeing the complete sequence a few times, the responses become memorized, such that seeing only a portion of the input sequence is enough to set off the entire response sequence.

![An animation of sequence memorization](https://raw.githubusercontent.com/mdabagia/nemo/master/docs/assets/images/seq_animation.gif){:style="display:block; margin-left:auto; margin-right:auto"}

A slight extension of this idea leads to faster memorization, when an additional auxiliary area communicates bidirectionally with the main area. This auxiliary area forms a sequence of its own, which becomes linked (or "scaffolded") with the main sequence and reinforces it. As a result, fewer presentations of the input sequence are required to achieve memorization.

![The setup for forming a scaffolded sequence of assemblies](https://raw.githubusercontent.com/mdabagia/nemo/master/docs/assets/images/scaffold_seq.png){:style="display:block; margin-left:auto; margin-right:auto"}
