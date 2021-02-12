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

**Zheng Zeng**, [Shiqiu (Edward) Liu](http://behindthepixels.io/), Jinglei Yang, [Lu Wang](http://vr.sdu.edu.cn/info/1010/1060.htm), [Ling-Qi Yan](https://sites.cs.ucsb.edu/~lingqi/)

*Computer Graphics Forum (Proceedings of Eurographics 2021)*

![](/images/pub_img_trmv.jpg){: .align-left width="360px" }

Existing texture synthesis usually suffers from several issues: non-learning based approaches, which mainly rely on iterative optimization, are usually very slow; recent deep learning-based approaches usually over-fit to a single texture image or a fixed set of texture images and therefore can't generalize to new unseen texture images. In this work, we present a deep learning framework that can do texture synthesis for arbitrary input texture image with output texture larger than the input in near real-time. Our framework is built on transpose convolution operation where the transpose convolution filters are the encoded features of the input texture and the transpose convolution inputs are the features' self-similarity maps. Visual and quantitative comparisons show that our method significantly out-performs prior methods while being hundreds of times faster.  

[Preprint (Coming soon...)](), [Video (Coming soon...)]()