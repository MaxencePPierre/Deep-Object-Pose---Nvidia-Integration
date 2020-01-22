# Deep-Object-Pose---Nvidia-Integration

This repository is a tutorial for embedding a Neural network for object detection through live camera streaming on a Nvidia Jetson nano.
The neural networkd used is official DOPE ROS package for detection and 6-DoF pose estimation of known objects from an RGB camera. The network has been trained on the following YCB objects: cracker box, sugar box, tomato soup can, mustard bottle, potted meat can, and gelatin box. 

The official repository is available here (https://github.com/NVlabs/Deep_Object_Pose)


## Requirements
 - A Nvidia Jetson nano with 4BG ram
 - A USB RGB Camera (in my case Kinect Asus Xtion)
 - The official package of deep pose object detection: https://github.com/NVlabs/Deep_Object_Pose
 - A desk fan or an Nvidia compatible
