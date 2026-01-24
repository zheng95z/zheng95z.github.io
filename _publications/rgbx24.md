---
layout: publication
time: 2024-07-15
title: "RGB↔X: Image Decomposition and Synthesis Using Material- and Lighting-aware Diffusion Models"
image: /assets/pub/rgbx24_small.png
publication: ACM SIGGRAPH Asia 2025 (Conference Track)
authors: <b>Zheng Zeng</b>, <a href="https://valentin.deschaintre.fr/" target="_blank">Valentin Deschaintre</a>, <a href="https://www.iliyan.com/" target="_blank">Iliyan Georgiev</a>, <a href="https://yannickhold.com/" target="_blank">Yannick Hold-Geoffroy</a>, <a href="https://yiweihu.netlify.app/" target="_blank">Yiwei Hu</a>, <a href="https://luanfujun.com/" target="_blank">Fujun Luan</a>, <a href="https://sites.cs.ucsb.edu/~lingqi/" target="_blank">Ling-Qi Yan</a>, <a href="http://www.miloshasan.net/" target="_blank">Miloš Hašan</a>
aka: "GenAI Models Can Eliminate/Simulate GI"
honor:
paper: /assets/files/sig24-rgbx.pdf
code: https://github.com/zheng95z/rgbx
slides: /assets/files/sig24-rgbx-slides.pdf
supplementary: https://drive.google.com/file/d/1ABfxTeD6Axw21PGhslP8n_JgYo5R6je4/view?usp=sharing
video:
doi: https://doi.org/10.1145/3641519.3657445
arxiv: https://arxiv.org/abs/2405.00666
teaser: /assets/pub/rgbx24_teaser.png
---

## What is RGB↔X?

RGB↔X is a unified diffusion-based framework that enables *realistic image analysis* (intrinsic channel estimation, denoted as RGB→X) and *synthesis* (realistic rendering given the intrinsic channels, denoted as X→RGB).

RGB↔X explores the connections between diffusion models, realistic rendering, and intrinsic decomposition. We believe it can bring benefits to a wide range of downstream tasks, including material editing, relighting, and realistic rendering from simple/under-specified scene definitions.

## Why using diffusion models on intrinsic decomposition?

The intrinsic decomposition problem is inherently diffcult due to its under-constrained nature, including the *ambiguity* between illumination and materials.

Consider this simple example:

<div style="text-align:center;">
        <img src="/assets/pub/rgbx24_ambiguity.png" style="max-width: 100%; height: auto;"/>
</div>

There are strong reflections and shadows on the wooden floor. Previous non-diffusion-model-based methods fail to recover the correct albedo channel.

<a href="https://peter-kocsis.github.io/IntrinsicImageDiffusion/" target="_blank">Recent amazing work by Kocsis et al.</a> has demonstrated improved estimation of intrinsic channels based on a diffusion model. They observe that further progress in this domain is likely to use generative modeling. We follow this direction further.

## Why using diffusion models on realistic rendering?

Typical generative models are simple to use but *hard to precisely control*. Quoting <a href="https://www.blenderguru.com/about" target="_blank">
Andrew Price</a> in his weekly 3D news about <a href="https://openai.com/sora" target="_blank">
Sora</a>: "Getting any result is easy. But getting a specific result is often impossible."

On the other hand, traditional rendering is precise but *requires full scene specification*, which is sometimes limiting.

We explore a middle ground where we specify only certain appearance properties that should be followed, and give freedom to the model to hallucinate a plausible version of the rest.

Having the (traditional) rendering knowledge in the diffusion framework could be the key to guarantee controllability and consistency. We believe this direction could enable applications like disentangled photo editing, fast previews of renderings for 3D software, CG-to-real approaches, and more.

<div class="notice--success" markdown="1">
<p style="margin-top:0px">💡 One interesting idea is to first obtain a normal map and irradiance map from the pure geometry and lightings, then use the X→RGB model to produce "rendering" images; following this, employ a differentiable renderer to optimize the material parameters based on these images. With this way, you'll have not only a preview of the rendering but also a full scene with corresponding materials that you can do further authoring. This entire process is possible to be simplified by using <a href="https://arxiv.org/pdf/2209.14988" target="_blank">the Score Distillation Sampling (SDS) technique</a>.</p>
</div>

## How does it work?

RGB↔X is enabled by two our fine-tuned diffusion models:

<div style="text-align:center;">
        <img src="/assets/pub/rgbx24_models.png" style="max-width: 100%; height: auto;"/>
</div>

The RGB→X model performs intrinsic decomposition: estimating per-pixel intrinsic channels (X) from an image (RGB).
- Repurpose the input text prompt as a “switch” to control the output and produce a single intrinsic channel at a time.
    - Enable usage of a mix of heterogeneous datasets, which differ in the available channels.
    - For example, a dataset with only albedo channel available can still be employed to train our model.

The X→RGB model synthesizes an image (RGB) from full or partial intrinsic channels (X).
- Channel drop-out training strategy: randomly drop conditioned channels during training.
    - Again, enable usage of a mix of heterogeneous datasets, which differ in the available channels.
    - Enable image generation with any subset of conditions.

## How well it works?

<div class="notice">
<h2 id="RGB→X results" style="margin-top:0px">RGB→X results</h2>
<div style="text-align:center;">
        <img src="/assets/pub/rgbx24_rgb2x.png" style="max-width: 100%; height: auto;"/>
</div>
</div>

<div class="notice">
<h2 id="X→RGB results" style="margin-top:0px">X→RGB results</h2>
<div style="text-align:center;">
        <img src="/assets/pub/rgbx24_x2rgb1.png" style="max-width: 100%; height: auto;"/>
</div>
<div style="text-align:center;">
        <img src="/assets/pub/rgbx24_x2rgb2.png" style="max-width: 100%; height: auto;"/>
</div>
</div>

<div class="notice">
<h2 id="RGB→X→RGB results" style="margin-top:0px">RGB→X→RGB results</h2>
<div style="text-align:center;">
        <img src="/assets/pub/rgbx24_rgb2x2rgb.png" style="max-width: 100%; height: auto;"/>
</div>
</div>

<div class="notice">
<h2 id="More results" style="margin-top:0px">Other interesting results: famous people and places</h2>
(Note that these images are clearly out of our training distribution.)

<div style="text-align:center;">
        <img src="/assets/pub/rgbx24_famous.png" style="max-width: 100%; height: auto;"/>
</div>
</div>

<div class="notice">
<h2 id="More results" style="margin-top:0px">Other interesting results: anime pictures</h2>
(Note that these images are clearly out of our training distribution. Thanks <a href="https://x.com/toyxyz3" target="_blank">toyxyz</a> for creating this!)

<div style="text-align:center;">
        <img src="/assets/pub/rgbx24_anime.jpg" style="max-width: 100%; height: auto;"/>
</div>
</div>

## Acknowledgments

We thank the anonymous reviewers for their constructive suggestions. We also thank [toyxyz](https://x.com/toyxyz3){:target="_blank"} for creating the ComfyUI Wrapper and the anime results! This work was done while Zheng was an intern at Adobe Research.

## Cite
```bib
@inproceedings{zeng2024rgb,
author = {Zeng, Zheng and Deschaintre, Valentin and Georgiev, Iliyan and Hold-Geoffroy, Yannick and Hu, Yiwei and Luan, Fujun and Yan, Ling-Qi and Ha\v{s}an, Milo\v{s}},
title = {RGB↔X: Image decomposition and synthesis using material- and lighting-aware diffusion models},
year = {2024},
isbn = {9798400705250},
publisher = {Association for Computing Machinery},
address = {New York, NY, USA},
url = {https://doi.org/10.1145/3641519.3657445},
doi = {10.1145/3641519.3657445},
booktitle = {ACM SIGGRAPH 2024 Conference Papers},
articleno = {75},
numpages = {11},
keywords = {Diffusion models, intrinsic decomposition, realistic rendering},
location = {Denver, CO, USA},
series = {SIGGRAPH '24}
}
```