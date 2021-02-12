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

### Transposer: Universal Texture Synthesis Using Feature Maps as Transposed Convolution Filter

**Guilin Liu, Rohan Taori, Ting-Chun Wang, Zhiding Yu, Shiqiu Liu, Fitsum A. Reda, Karan Sapra, Andrew Tao, Bryan Catanzaro**

![](/images/pub_img_trmv.jpg){: .align-left width="360px" }

Existing texture synthesis usually suffers from several issues: non-learning based approaches, which mainly rely on iterative optimization, are usually very slow; recent deep learning-based approaches usually over-fit to a single texture image or a fixed set of texture images and therefore can't generalize to new unseen texture images. In this work, we present a deep learning framework that can do texture synthesis for arbitrary input texture image with output texture larger than the input in near real-time. Our framework is built on transpose convolution operation where the transpose convolution filters are the encoded features of the input texture and the transpose convolution inputs are the features' self-similarity maps. Visual and quantitative comparisons show that our method significantly out-performs prior methods while being hundreds of times faster.  

[Preprint](https://arxiv.org/pdf/2007.07243.pdf), [Video](https://www.youtube.com/watch?v=8Us9c5iBRCY)