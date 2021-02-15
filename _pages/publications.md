---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

<!-- {% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single-pub.html %}
{% endfor %} -->

---

# Temporally Reliable Motion Vectors for Real-time Ray Tracing

**Zheng Zeng**, [Shiqiu (Edward) Liu](http://behindthepixels.io/){:target="_blank"}, Jinglei Yang, [Lu Wang](http://vr.sdu.edu.cn/info/1010/1060.htm){:target="_blank"}, [Ling-Qi Yan](https://sites.cs.ucsb.edu/~lingqi/){:target="_blank"}

*Computer Graphics Forum (Proceedings of Eurographics 2021)*

![](/images/pub_img_trmv.jpg){: .align-left width="360px" }

Real-time ray tracing (RTRT) is being pervasively applied. The key to RTRT is a reliable denoising scheme that reconstructs clean images from significantly undersampled noisy inputs, usually at 1 sample per pixel as limited by current hardware's computing power. The state of the art reconstruction methods all rely on temporal filtering to find correspondences of current pixels in the previous frame, described using per-pixel screen-space motion vectors. While these approaches are demonstrated powerful, they suffer from a common issue that the temporal information cannot be used when the motion vectors are not valid, i.e. when temporal correspondences are not obviously available or do not exist in theory.

We introduce temporally reliable motion vectors that aim at deeper exploration of temporal coherence, especially for the generally-believed difficult applications on shadows, glossy reflections and occlusions, with the key idea to detect and track the cause of each effect. We show that our temporally reliable motion vectors produce significantly better temporal results on a variety of dynamic scenes when compared to the state of the art methods, but with negligible performance overhead.

[Paper](https://sites.cs.ucsb.edu/~lingqi/publications/paper_trmv.pdf){:target="_blank"}, [Video (628M)](https://sites.cs.ucsb.edu/~lingqi/publications/video_trmv.pdf){:target="_blank"}

---

# Joint SVBRDF Recovery and Synthesis From a Single Image using an Unsupervised Generative Adversarial Network

Yezi Zhao, [Beibei Wang](https://wangningbei.github.io/){:target="_blank"}, [Yanning Xu](http://vr.sdu.edu.cn/info/1010/1062.htm){:target="_blank"}, **Zheng Zeng**, [Lu Wang](http://vr.sdu.edu.cn/info/1010/1060.htm){:target="_blank"}, [Nicolas Holzschuch](http://maverick.inria.fr/Membres/Nicolas.Holzschuch/){:target="_blank"}

*Eurographics Symposium on Rendering (DL-only Track) (2020)*

![](/images/pub_img_svbrdfgan.jpg){: .align-left width="400px" }

We want to recreate spatially-varying bi-directional reflectance distribution functions (SVBRDFs) from a single image. Pro- ducing these SVBRDFs from single images will allow designers to incorporate many new materials in their virtual scenes, increasing their realism. A single image contains incomplete information about the SVBRDF, making reconstruction difficult. Existing algorithms can produce high-quality SVBRDFs with single or few input photographs using supervised deep learning. The learning step relies on a huge dataset with both input photographs and the ground truth SVBRDF maps. This is a weakness as ground truth maps are not easy to acquire. For practical use, it is also important to produce large SVBRDF maps. Existing algorithms rely on a separate texture synthesis step to generate these large maps, which leads to the loss of consistency be- tween generated SVBRDF maps. In this paper, we address both issues simultaneously. We present an unsupervised generative adversarial neural network that addresses both SVBRDF capture from a single image and synthesis at the same time. From a low-resolution input image, we generate a large resolution SVBRDF, much larger than the input images. We train a generative adversarial network (GAN) to get SVBRDF maps, which have both a large spatial extent and detailed texels. We employ a two-stream generator that divides the training of maps into two groups (normal and roughness as one, diffuse and specular as the other) to better optimize those four maps. In the end, our method is able to generate high-quality large scale SVBRDF maps from a single input photograph with repetitive structures and provides higher quality rendering results with more details compared to the previous works. Each input for our method requires individual training, which costs about 3 hours.

[Paper](/files/egsr2020-svbrdf-gan.pdf){:target="_blank"}, [Code](https://github.com/mengshu1996/SVBRDF-GAN){:target="_blank"}

---

# Denoising SPPM Renderings Using a Multi-Residual Network

**Zheng Zeng**, [Lu Wang](http://vr.sdu.edu.cn/info/1010/1060.htm){:target="_blank"}, [Beibei Wang](https://wangningbei.github.io/){:target="_blank"}, Chunmeng Kang, [Yanning Xu](http://vr.sdu.edu.cn/info/1010/1062.htm){:target="_blank"}

*Journal of Computer Science and Technology, 2020, 35: 506-521.*

![](/images/pub_img_sppmdenoiser.jpg){: .align-left width="360px" }

Stochastic progressive photon mapping (SPPM) is one of the important global illumination methods in computer graphics. It can simulate caustics and specular-diffuse-specular lighting effects efficiently. However, as a biased method, it always suffers from both bias and variance with limited iterations, and the bias and the variance bring multi-scale noises into SPPM renderings. Recent learning-based methods have shown great advantages on denoising unbiased Monte Carlo (MC) methods, but have not been leveraged for biased ones. In this paper, we present the first learning-based method specially designed for denoising-biased SPPM renderings. Firstly, to avoid conflicting denoising constraints, the radiance of final images is decomposed into two components: caustic and global. These two components are then denoised separately via a two-network framework. In each network, we employ a novel multi-residual block with two sizes of filters, which significantly improves the model’s capabilities, and makes it more suitable for multi-scale noises on both low-frequency and high-frequency areas. We also present a series of photon-related auxiliary features, to better handle noises while preserving illumination details, especially caustics. Compared with other state-of-the-art learning-based denoising methods that we apply to this problem, our method shows a higher denoising quality, which could efficiently denoise multi-scale noises while keeping sharp illuminations.

[Paper](/files/jcst2020-sppm-denoiser.pdf){:target="_blank"}