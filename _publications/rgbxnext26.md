---
layout: publication
time: 2026-08-14
title: "RGBX-Next: Towards Realistic Generative Rendering from G-Buffers"
image: /assets/pub/rgbxnext26_small.png
publication: arXiv preprint, 2026
authors: <b>Zheng Zeng</b>, Marco Salvi, <a href="https://winmad.github.io/" target="_blank">Lifan Wu</a>, Jan Novák, <a href="https://dqlin.xyz/" target="_blank">Daqi Lin</a>, Saeed Hadadan, Yichen Sheng, Robert Pottorff, Shiqiu Liu, <a href="https://cseweb.ucsd.edu/~ravir/" target="_blank">Ravi Ramamoorthi</a>, <a href="https://lingqiyan.github.io/" target="_blank">Lingqi Yan</a>, <a href="http://www.miloshasan.net/" target="_blank">Miloš Hašan</a>
aka:
honor:
paper:
code:
slides:
supplementary:
video:
arxiv: https://arxiv.org/abs/2608.13929
doi:
teaser: /assets/pub/rgbxnext26_teaser.png
---

## What is RGBX-Next?

RGBX-Next extends [RGB↔X](/publications/rgbx24.html) to images, videos, and streams. Our unified framework learns both directions: estimating G-buffers from RGB inputs (RGB→X), and generating realistic RGB outputs conditioned on G-buffers (X→RGB).

We present a recipe for adapting diffusion transformer (DiT) models to forward and inverse rendering. Training with real video data improves rendering realism, while flexible G-buffer conditioning balances explicit control with generative freedom. Streaming extensions support coherent forward and inverse rendering over long sequences.

## Cite

{% raw %}
```bibtex
@misc{zeng2026rgbxnext,
  title = {{RGBX-Next}: Towards Realistic Generative Rendering from {G-Buffers}},
  author = {Zeng, Zheng and Salvi, Marco and Wu, Lifan and Novák, Jan and Lin, Daqi and Hadadan, Saeed and Sheng, Yichen and Pottorff, Robert and Liu, Shiqiu and Ramamoorthi, Ravi and Yan, Lingqi and Hašan, Miloš},
  year = {2026},
  eprint = {2608.13929},
  archivePrefix = {arXiv},
  primaryClass = {cs.CV},
  url = {https://arxiv.org/abs/2608.13929}
}
```
{% endraw %}
