---
layout: publication
time: 2022-09-13
title: "Temporally Reliable Motion Vectors for Real-time Ray Tracing"
image: /assets/pub/trmv21_small.png
publication: Eurographics 2021 (CGF track)
authors: <b>Zheng Zeng</b>, <a href="http://behindthepixels.io/" target="_blank">Shiqiu (Edward) Liu</a>, Jinglei Yang, <a href="http://vr.sdu.edu.cn/info/1010/1060.htm" target="_blank">Lu Wang</a>, <a href="https://lingqiyan.github.io/" target="_blank">Lingqi Yan</a>
aka: different motion vectors for different effects
honor:
paper: https://sites.cs.ucsb.edu/~lingqi/publications/paper_trmv.pdf
code:
slides: /assets/files/TRMV_EG_2021.pptx
supplementary:
video: https://sites.cs.ucsb.edu/~lingqi/publications/video_trmv.mp4
doi: https://doi.org/10.1111/cgf.142616
teaser: /assets/pub/trmv21_teaser.png
page: 
---

## Abstract
Real-time ray tracing (RTRT) is being pervasively applied. The key to RTRT is a reliable denoising scheme that reconstructs clean images from significantly undersampled noisy inputs, usually at 1 sample per pixel as limited by current hardware’s computing power. The state of the art reconstruction methods all rely on temporal filtering to find correspondences of current pixels in the previous frame, described using per-pixel screen-space motion vectors. While these approaches are demonstrated powerful, they suffer from a common issue that the temporal information cannot be used when the motion vectors are not valid, i.e. when temporal correspondences are not obviously available or do not exist in theory.
We introduce temporally reliable motion vectors that aim at deeper exploration of temporal coherence, especially for the generally-believed difficult applications on shadows, glossy reflections and occlusions, with the key idea to detect and track the cause of each effect. We show that our temporally reliable motion vectors produce significantly better temporal results on a variety of dynamic scenes when compared to the state of the art methods, but with negligible performance overhead.

## Cite
```
@inproceedings{zeng2021temporally,
  title={Temporally Reliable Motion Vectors for Real-time Ray Tracing},
  author={Zeng, Zheng and Liu, Shiqiu and Yang, Jinglei and Wang, Lu and Yan, Lingqi},
  booktitle={Computer Graphics Forum},
  volume={40},
  number={2},
  pages={79--90},
  year={2021},
  organization={Wiley Online Library}
}
```