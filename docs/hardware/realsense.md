---
title: Intel RealSense
parent: Hardware 
nav_order: 30
---

# Intel RealSense RGBD Camera

Model Number:
D435

Product page:
[https://realsenseai.com/products/stereo-depth-camera-d435/]

ROS wrapper:
[https://github.com/IntelRealSense/realsense-ros]

## Realsense SDK

Installation instructions for the RealSense SDK and the ROS wrapper can be found in the realsense-ros readme. If you are using a Jetson then follow the Jetson install instructions, otherwise use the appropriate Ubuntu install instructions. Once the RealSense SDK has been installed `realsense-viewer` can be used to view sensor data from the camera. The ROS wrapper can be used to publish RGB images, depth images, and point cloud data as ROS topics

## RGBD image format

RGB image encoding: bgr8
Depth image encoding: 16UC1

Each pixel in the depth image has a 16bit unsigned number associated with it representing the depth of that pixel in millimeters. If the depth reading is invalid for any reason, this value will be 0

----

[https://realsenseai.com/products/stereo-depth-camera-d435/]: https://realsenseai.com/products/stereo-depth-camera-d435/
[https://github.com/IntelRealSense/realsense-ros]: https://github.com/IntelRealSense/realsense-ros
