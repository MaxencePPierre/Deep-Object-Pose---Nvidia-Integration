# Deep-Object-Pose---Nvidia-Integration

This repository is a tutorial for embedding a Neural network for object detection through live camera streaming on a Nvidia Jetson nano.
The neural networkd used is the official DOPE ROS package for detection and 6-DoF pose estimation of known objects from an RGB camera. The network has been trained on the following YCB objects: cracker box, sugar box, tomato soup can, mustard bottle, potted meat can, and gelatin box. 

The official repository is available [here] (https://github.com/NVlabs/Deep_Object_Pose)


## Requirements
 - A Nvidia Jetson nano with at least 4BG ram
 - Micro-USB power supply 5V - 2A for Nvidia Jetson (I used the official raspberry Pi one)
 - A USB RGB Camera (I used a Kinect Asus Xtion)
 - The [official package] of deep pose object detection https://github.com/NVlabs/Deep_Object_Pose
 - A desk fan or an Nvidia Jetson compatible one


## Setup
I strongly advise you to start from scratch and flash the Jetson Nano Developer Kit SD Card [Image] (https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit#write) on an clean SD card.

Once you flashed the Nvidia Image on the SD card, put it in the Jetson Nano and switch it on. I also advise you to start in the same time the fan for best performance (I will go back to its importance later).

I have tested on Ubuntu 16.04 with ROS Melodic with an NVIDIA Jetson Nano with python 2.7 (and thus pip). The code may work on other systems.

One the Nvidia started, you can follow the repository of [Deep Pose object] https://github.com/NVlabs/Deep_Object_Pose step by step 
until:

```
pip install -r requirements.txt
```
