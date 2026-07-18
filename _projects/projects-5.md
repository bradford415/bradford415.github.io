---
title: "ROS 2 Object Detection Pipeline"
excerpt: "ROS 2 object detection pipeline in Gazebo Sim and a differential drive robot<br/><img src='/images/ros2_obj_det.gif'>"
collection: projects
---

[Project code](https://github.com/bradford415/perception-bot)

For this project, I created a differential drive robot in ROS 2 (C++ and Python) and Gazebo Sim to to learn more of the broader perception/computer vision field and how to apply it to robotics. Right now the project is still in progress and only in simulation but I'm currently working towards building the bot in person and deploying this pipeline to a Jetson Nano. Below demonstrates current features of the robot.

<span style="font-size: 24px;"><strong>Real-time object detection with RT-DETRv2 and ONNXRuntime</strong></span><br/>
To get to the point of generating perception nodes in ROS, the first steps were to setup the differential drive robot in ROS and Gazebo Sim. Next, I trained an [RT-DETRv2](https://arxiv.org/abs/2407.17140) model on the COCO dataset to use as the baseline for object detection. RT-DETRv2 was selected as most robotic use cases require real-time inference. Next, the model was converted to ONNX format for platform agnostic inference and graph optimizations. On the ROS side, an object detection node was created in C++ which is responsible for reading and preprocessing camera images, running GPU-enabled inference through ONNXRuntime, postprocessing the detections, and visualizing the output.

For next steps, I'm currently building small version of the differential drive robot and will deploy the ROS 2 code to a Jetson Nano.


<iframe width="560" height="315" src="https://www.youtube.com/embed/WWM5wiIM9sQ?si=M9-jQ4BSlRua79f_" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>