# Deep-Object-Pose---Nvidia-Integration

This repository is a tutorial for embedding a Neural network for object detection through live camera streaming on a Nvidia Jetson nano.
The neural networkd used is the official DOPE ROS package for detection and 6-DoF pose estimation of known objects from an RGB camera. The network has been trained on the following YCB objects: cracker box, sugar box, tomato soup can, mustard bottle, potted meat can, and gelatin box. 

The official repository is available [here](https://github.com/NVlabs/Deep_Object_Pose).


## Requirements
 - A Nvidia Jetson nano with at least 4BG ram
 - Micro-USB power supply 5V - 2A for Nvidia Jetson (I used the official raspberry Pi one)
 - A USB RGB Camera (I used a Kinect Asus Xtion)
 - Download the [official package](https://github.com/NVlabs/Deep_Object_Pose) of deep pose object detection 
 - A desk fan or an Nvidia Jetson compatible one


## Setup
I strongly advise you to start from scratch and flash the Jetson Nano Developer Kit SD Card [Image](https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit#write) on an clean SD card.

Once you flashed the Nvidia Image on the SD card, put it in the Jetson Nano and switch it on. I also advise you to start in the same time the fan for best performance (I will go back to its importance later).

I have tested on Ubuntu 16.04 with ROS Melodic with an NVIDIA Jetson Nano with python 2.7 (and thus pip). The code may work on other systems.


One the Nvidia started, you can follow the repository of [Deep Pose object](https://github.com/NVlabs/Deep_Object_Pose) installation step by step until:

```
$ pip install -r requirements.txt
```

Here you might have some trouble instaling libraries versions with the ones compatibles with the Nvidia Jeton Nano. In this repository, I added a requirement.txt file which contains all versions of the libraries that I was able to install. But in any case, I strongly advise you to install them one by one instead of running the command with the requirements.txt file.

Then you can follow steps 5 and 6 of the Installation process, but remember to replace *kinetic* by *melodic*.


## Running

- **1 Start ROS master**
```
$ cd ~/catkin_ws
$ source devel/setup.bash
$ roscore
```

- **2 Start camera node**
```
$ cd catkin_ws
$ source devel/setup.bash
$ roslaunch openni2_launch openni2.launch
```

- **3 Edit config file**
As I am using a USB camera, you need to edit the config file at ```~/catkin_ws/src/dope/config/config_pose.yaml``` and change the two first lines to:
```
topic_camera: "/camera/rgb/image_raw"
topic_camera_info: "/camera/rgb/camera_info"
```
 All the other parameters are detailled in the Deep Pose Object repository.

- **4 Start DOPE node**
```
$ cd catkin_ws
$ source devel/setup.bash
$ roslaunch openni2_launch openni2.launch
```




Citation
@inproceedings{tremblay2018corl:dope,
 author = {Jonathan Tremblay and Thang To and Balakumar Sundaralingam and Yu Xiang and Dieter Fox and Stan Birchfield},
 title = {Deep Object Pose Estimation for Semantic Robotic Grasping of Household Objects},
 booktitle = {Conference on Robot Learning (CoRL)},
 url = "https://arxiv.org/abs/1809.10790",
 year = 2018
}

