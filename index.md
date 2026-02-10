---
layout: distill
title: "Synthetic Data Efficiency"
# permalink: /main/
date: 2026-02-09
description: "Your article description goes here. This will appear as the subtitle on the page and in search engine results."
future: true
htmlwidgets: true
hidden: false

authors:
  - name: Konwoo Kim
    url: "https://github.com/konwoo"
    # affiliations:
    #   name: Your Affiliation
    #   url: "https://affiliation-url.com"

# Table of contents — update these to match your ## and ### headings
toc:
  - name: Introduction
  - name: Background
    subsections:
      - name: Synthetic Data
      - name: Data Efficiency
  - name: Methods
  - name: Results
  - name: Discussion
  - name: Conclusion
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

`Last Update: Feb 9th 2026`

## <mark style='background-color: #fff5b1'> Introduction </mark> {#introduction}

Your introduction goes here. You can use **bold**, *italic*, `inline code`, and [links](https://example.com).

You can write inline math like $$x^2 + y^2 = z^2$$ and display math:

$$
\begin{aligned}
& L(\theta) = \mathbb{E}_{(x,y) \sim \mathcal{D}} \left[ \ell(f_\theta(x), y) \right]
\end{aligned}
$$

> Blockquotes look like this.

## <mark style='background-color: #fff5b1'> Background </mark> {#background}

### Synthetic Data

Content about synthetic data...

### Data Efficiency

Content about data efficiency...

<!-- Example of how to add an image:
![figure_name](/assets/img/your_figure.png){: width="100%"}
*Fig. Your figure caption. Source from [Paper Title](https://arxiv.org/abs/XXXX.XXXXX)*
-->

## <mark style='background-color: #fff5b1'> Methods </mark> {#methods}

You can include tables:

| Method | Dataset | Performance |
|--------|---------|-------------|
| Baseline | Real Data | 85.2 |
| Ours | Synthetic + Real | 89.7 |

And code blocks:

```python
import torch
import torch.nn as nn

model = nn.Transformer(
    d_model=512,
    nhead=8,
    num_encoder_layers=6,
)
```

## <mark style='background-color: #fff5b1'> Results </mark> {#results}

Your results here...

## <mark style='background-color: #fff5b1'> Discussion </mark> {#discussion}

Your discussion here...

## <mark style='background-color: #fff5b1'> Conclusion </mark> {#conclusion}

Your conclusion here...

## <mark style='background-color: #fff5b1'> References </mark> {#references}

* [Paper 1 Title](https://arxiv.org/abs/XXXX.XXXXX)
* [Paper 2 Title](https://arxiv.org/abs/XXXX.XXXXX)
