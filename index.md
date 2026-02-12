---
layout: distill
title: "Synthetic Data Efficiency"
# permalink: /main/
date: 2026-02-11
description: "synthetic data tutorial for data efficiency."
future: true
htmlwidgets: true
hidden: false

authors:
  - name: Konwoo Kim*
    url: "https://konwoo.kim/"
  - name: Suhas Kotha*
    url: "https://kothasuhas.github.io/index.html"
  - name: Advisors

# Table of contents — update these to match your ## and ### headings
toc:
  - name: Introduction
  - name: Setting
    subsections:
      - name: Data Efficiency Setup
      - name: Synthetic Data
  - name: Synth data science (or How to WRAP)
    subsections:
      - name: Fix a big pool of synth data
      - name: Scaling with synthetic copies
  - name: Synth data should use up your context
    subsections:
      - name: How to sort synthetic data
      - name: Benefit of sorting
      - name: Cot data
  - name: Synth data is different from self-distill
    subsections:
      - name: WRAP vs self-distill
      - name: Composition with Ensembling
  - name: Conclusion
  - name: Related Work
  - name: References

# Additional styles for the article
_styles: >
  .fake-img {
    background: #bbb;
    border: 1px solid rgba(0, 0, 0, 0.1);
    box-shadow: 0 0px 4px rgba(0, 0, 0, 0.1);
    margin-bottom: 12px;
  }
  .fake-img p {
    font-family: monospace;
    color: white;
    text-align: left;
    margin: 12px 0;
    text-align: center;
    font-size: 16px;
  }
  /* scrollable table style */
  table {
    display: block;
    overflow-x: auto;
    white-space: nowrap;
  }
---


## Introduction

* Data efficiency is a big problem because compute grows faster than data 
* People believe synthetic data is one solution for data efficiency 
  * Synthetic data is increasingly used for pre-training models: x, y, z
  * Synthetic data generally observed to help on downstream tasks 
* In this post, we take a controlled data efficiency setup and carefully investigate how to best use synthetic data. We prescribe how to train with synthetic data and several new properties of synthetic data 
  * Synth data science 
    * Synth data gives an iid val loss win 
    * Synth data doesn’t increase the amount you can train on real data
    * Synth data isn’t an infinite compute lever 
      * Given a fixed amount of synth data, you will overfit 
      * Too much synth data doesn’t help 
  * Synth data should use up your context 
    * Inspired by ICPT, we show that sorted WRAP is a free win for both iid val loss and arxiv (or some other long-context loss) over shuffled WRAP 
    * We show some design decisions on how to sorting, mention epiplexity 
    * We show that other kinds of synth data (cot) which naturally expand the document also benefit from this 
  * Synth data is different from self-distill 
    * In isolation, WRAP and self-distill have the same loss 
    * Self-distill doesn’t compose with ensembling, as we expect from intuition, but WRAP does compose  


## Setting 

### Data Efficiency Setup
  * 203M tokens of DCLM data, 1M tokens of iid val 
  * 150M, 300M, 600M, 1.5B dense models like infinite compute with joint scaling 
  * Convex tuning of lr, wd, epoch
  * Arxiv loss for long-context proxy 
  * Show recreated regularized model scaling plot here
![regularized_scaling](/assets/img/regularized_scaling.png){: width="100%"}

### Synthetic Data
  * Generated with Llama 3.1 8B instruct + tokasaurus, include prompts somewhere
  * Mixing ratio between real : synth data 
  * Amount of synth data (for rephrasing, number of copies per document) 

## Synth data science (or How to WRAP)
### Fix a big pool of synth data
  * Sweep real epoch (1,2,4,8,16,32)
  * Ratio (0.5, 0.75, 0.9)
  * wd (0.4, 0.8)

Better than regularized, optimal real epochs is the same, kx more total tokens to train on, overfits with too high of a mixing ratio 
![synth_data_science](/assets/img/synth_data_science_hypers.png){: width="100%"}

### Scaling with synthetic copies
  * For each copy rate, search real data epoch count, ratio, wd 

Can't scale synthetic copies infinitely (only show shuffled)
![synth_data_copy_scaling](/assets/img/copy_scaling.png){: width="100%"}


## Synth data should use up your context
* Inspired by ICPT, we propose to put related synthetic data next to each other (sorting) 

### How to sort synthetic data
* No real doc, real doc in the back, real doc in the back 
* Real doc in the back is best, true for both 2 copies and 8 copies 
* Related to epiplexity 

![cpr2](/assets/img/cpr2.png){: width="100%"}
![cpr8](/assets/img/cpr8.png){: width="100%"}

### Benefit of sorting 
Across synthetic copy scales, both losses, sorting > shuffled 
![synth_data_copy_scaling](/assets/img/copy_scaling.png){: width="100%"}

### Cot data
We consider a different form of synthetic data that naturally expands the document. It's even better. 
![cot_scaling](/assets/img/cot_scaling.png){: width="100%"}

## Synth data is different from self-distill 

### WRAP vs self-distill 
They look the same in isolation. 
![wrap_vs_sd](/assets/img/wrap_vs_sd.png){: width="100%"}
### Composition with Ensembling
We recreate ensembles.
![ensemble_scaling](/assets/img/ensemble_scaling.png){: width="100%"}
We find that WRAP composes with ensembles.
![ensemble_scaling_wrap](/assets/img/ensemble_scaling_wrap.png){: width="100%"}
We find self-distill doesn't compose with ensembling cause it's like a 2-ensemble.
![ensemble_scaling_wrap_sd](/assets/img/ensemble_scaling_wrap_sd.png){: width="100%"}

## Conclusion

## Related Work 

## References
