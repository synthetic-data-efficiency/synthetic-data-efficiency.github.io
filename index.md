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
  - name: Science of synthetic data
    subsections:
      - name: Setting
      - name: Tuning synthetic data
      - name: Scaling synthetic tokens
      - name: Rephrasing vs. Self-Distill
  - name: Synth data should use up your context
    subsections:
      - name: How to sort synthetic data
      - name: Scaling synthetic tokens
  - name: Creating context with latent thoughts
    subsections:
      - name: Latent Thoughts
  - name: Conclusion
  - name: Related Work
  - name: Appendix
    subsections:
      - name: Hyperparameter tuning
      - name: Cross-document attention 
      - name: Ensembling composition with synthetic data
      - name: Synthetic data prompts
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
## Science of synthetic data

### Setting
### Tuning synthetic data
### Scaling synthetic tokens
![rephrase_scaling_shuffled](/assets/img/rephrase_scaling_shuffled.png){: width="100%"}
### Rephrasing vs. Self-Distill
![ensemble_wrap](/assets/img/ensemble_wrap.png){: width="100%"}

## Synth data should use up your context
### How to sort synthetic data
![sorting_design](/assets/img/sorting_design.png){: width="100%"}
### Scaling synthetic tokens
![rephrase_scaling_shuffled_sorted](/assets/img/rephrase_scaling_shuffled_sorted.png){: width="100%"}
![rephrase_scaling_shuffled_sorted_arxiv](/assets/img/rephrase_scaling_shuffled_sorted_arxiv.png){: width="100%"}

## Creating context with latent thoughts

### Latent Thoughts
![latent](/assets/img/latent.png){: width="100%"}

## Conclusion

## Related Work 

## Appendix 

### Hyperparameter tuning
![loss_vs_epochs_s16](/assets/img/loss_vs_epochs_s16.png){: width="100%"}
![loss_vs_epochs](/assets/img/loss_vs_epochs.png){: width="100%"}

### Cross-document attention 
![cda_ablation](/assets/img/cda_ablation.png){: width="100%"}

### Ensembling composition with synthetic data
![ensemble_all](/assets/img/ensemble_all.png){: width="100%"}

### Synthetic data prompts


## References
