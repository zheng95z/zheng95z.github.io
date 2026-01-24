---
layout: publication
time: 2020-09-13
title: "Denoising Stochastic Progressive Photon Mapping Renderings Using a Multi-Residual Network"
image: /assets/pub/sppmdenoiser20_small.png
publication: Journal of Computer Science and Technology (CVM2020)
authors: <b>Zheng Zeng</b>, <a href="http://vr.sdu.edu.cn/info/1010/1060.htm" target="_blank">Lu Wang</a>, <a href="https://wangningbei.github.io/" target="_blank">Beibei Wang</a>, Chun-Meng Kang, <a href="http://vr.sdu.edu.cn/info/1010/1062.htm" target="_blank"> Yanning Xu</a>
aka: different receptive fields for different scales of noise
honor:
paper: /assets/files/jcst2020-sppm-denoiser.pdf
code:
slides: /assets/files/jcst2020-sppm-denoiser-pre.pdf
supplementary:
video: 
doi: https://doi.org/10.1007/s11390-020-0264-1
teaser: /assets/pub/sppmdenoiser20_teaser.png
page: 
---

## Abstract
Stochastic progressive photon mapping (SPPM) is one of the important global illumination methods in computer graphics. It can simulate caustics and specular-diffuse-specular lighting effects efficiently. However, as a biased method, it always suffers from both bias and variance with limited iterations, and the bias and the variance bring multi-scale noises into SPPM renderings. Recent learning-based methods have shown great advantages on denoising unbiased Monte Carlo (MC) methods, but have not been leveraged for biased ones. In this paper, we present the first learning-based method specially designed for denoising-biased SPPM renderings. Firstly, to avoid conflicting denoising constraints, the radiance of final images is decomposed into two components: caustic and global. These two components are then denoised separately via a two-network framework. In each network, we employ a novel multi-residual block with two sizes of filters, which significantly improves the model’s capabilities, and makes it more suitable for multi-scale noises on both low-frequency and high-frequency areas. We also present a series of photon-related auxiliary features, to better handle noises while preserving illumination details, especially caustics. Compared with other state-of-the-art learning-based denoising methods that we apply to this problem, our method shows a higher denoising quality, which could efficiently denoise multi-scale noises while keeping sharp illuminations.


## Cite
```bib
@article{zeng2020denoising,
  title={Denoising stochastic progressive photon mapping renderings using a multi-residual network},
  author={Zeng, Zheng and Wang, Lu and Wang, Bei-Bei and Kang, Chun-Meng and Xu, Yan-Ning},
  journal={Journal of Computer Science and Technology},
  volume={35},
  pages={506--521},
  year={2020},
  publisher={Springer}
}
```