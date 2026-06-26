---
title: "Open-Vocabulary Object Detection on Sythentic Aperture Radar Images"
excerpt: "Evaulating fine-tuning an open-vocabulary object detection model on synthetic aperture radar images<br/><img src='/images/open_vocab_example_1.png'>"
collection: projects
---

This project evaluated the viability of fine-tuning GroundingDINO, an open-vocabulary object detection model, on synthetic aperture radar images (SAR), a very complex domain in remote sensing. SAR measures the radar energy return and, depending on the material/surface, generates a silhoutte-like grayscale image of the ground. The brighter the pixel in the SAR image, the higher energy return it has. Therefore, it can be very challenging to discern the objects or scene in the image.

Due to the complex domain, open-source object detection datasets are hard to come across as it usually requires another modality to label the dataset. Additionally, open-vocabulary models like GroundDINO are typically trained with groudning labels, text captions describing a region in the image. Open-source grounding labels of SAR images is almost non-existent. Luckily, GroundingDINO supports training with regular object detection labels or grounding labels. When using solely object detection labels, the text labels are synthesized from the bounding box classes. For example, if there are two boxes of a `car` and a `person`, the text input sequence is `car . person .`

For this project, the open-source SAR object detection dataset `SARDet-100k` was utilized to fine-tune a pretrained GroundingDINO model with pure object detection labels. Ultimately, the model was able to perform regular closed-set object on the objects it was trained on very well. However, unsuprisingly, it struggled to discover completely novel objects outside it's fine-tuning data. At the moment, the closest the model gets to detecting novel objects is to provide a text query which is a synonym of the objects in the fine-tuning class set.

Example 1: The top image has a `bridge` and two `ship`s in the image. After fine-tuning, the model is able to localize and classify the bridge and both ships as `boat`s. The classs `boat` was not used to fine-tune the model.

Example 2: The bottom image has two `aircraft`s in the image annd the model is able to localize and classify these aircrafts as planes when the input text is `plane .` is used. The class `plane` was not used to fine-tune the model.

**NOTE**: Inference shown is from the test set.

<img src='/images/open_vocab_example_2.png'>

<br/>

<img src='/images/open_vocab_example_1.png'>


## References
<sup>1</sup> Liu, Shilong, et al. "Grounding dino: Marrying dino with grounded pre-training for open-set object detection." European conference on computer vision. Cham: Springer Nature Switzerland, 2024.
