---
title: "Real-Time Semantic Segmentation"
excerpt: "Real-time semantic segmentation inference on a laptop<br/><img src='/images/swift-net-sem-seg-demo.gif'>"
collection: projects
---

This project was a part of my graduate school research to train an efficient semantic segmentation model for off-road environments and deploy the model on an autonomous Husky Robot.

The model used in the first video (top) is the SwiftNet<sup>1</sup> semantic segmentation model which runs very efficiently on low-compute devices, like a laptop GPU. The fast inference speed is mostly a result of an efficient model architecture. SwiftNet uses a ResNet-18 backbone and a mutli-branch architecture to fuse intermediate feature maps during the upsampling stage of semantic segmentation. Thee ResNet-18 backbone allows quick processing of high-resolution images and the multi-branch design maintains it's strong intersection over union (IoU) metric. Achieves and average of __22 fps__ on a laptop GPU.

The second part of this project looks at improving temporal consistency temporal consistency. Notice in the first video, the semgentation map on the right flickers between classes (colors), this means that the class predictions between frames are temporally inconsistent. To address this, the AuxAdapt <sup>2</sup> method was implemented. The idea behind AuxAdapt is to use a tiny auxiliary network at a lower spatial resolution together with the main segmentation network. During test-time, the main network is frozen and only the auxiliary network is updated. The outputs from both networks are summed before computing the logits. The result is shown from the video at the bottom, where the segmentation map is much smoother between frames (right) than only the segmentation map from the main network (left).


<iframe width="560" height="315" src="https://www.youtube.com/embed/DvSOB60E_EY?si=pf9HIK53YU1yActa" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<br/>

<iframe width="560" height="315" src="https://www.youtube.com/embed/jGcOne07_WE?si=FwfWpVvPWPrtCLxk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<br/>

<sup>1</sup> Wang, Haochen, et al. "Swiftnet: Real-time video object segmentation." Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. 2021.

<sup>2</sup> Zhang, Yizhe, et al. "Auxadapt: Stable and efficient test-time adaptation for temporally consistent video semantic segmentation." Proceedings of the IEEE/CVF Winter Conference on Applications of Computer Vision. 2022.