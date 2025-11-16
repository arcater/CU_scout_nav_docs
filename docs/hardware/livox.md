---
title: Livox HAP
parent: Hardware 
nav_order: 11
---

# Livox HAP

Product Webpage:
[https://www.livoxtech.com/hap]

ROS driver:
[https://github.com/Livox-SDK/livox_ros_driver2]

Link to Livox user manual (3rd party site):
[https://terra-1-g.djicdn.com/65c028cd298f4669a7f0e40e50ba1131/Livox%20HAP%20(TX)%20User%20Manual.pdf]

## Configuration

The Livox HAP connects to the PC via an ethernet cable. The network settings on the PC must be properly configured to successfully communicate with the LiDAR sensor. The default IP addresse and subnet masks for the sensor and PC can be found in the table below (taken from Livox HAP manual). Programs such as `wireshark` can be used to analyze the network messages coming from the LiDAR sensor to determine the sensor IP and the expected PC IP.

| Device       | Default IP        | Default Subnet Mask  |
|:-------------|:------------------|:---------------------|
| Livox HAP    | 192.168.1.200     | 255.255.255.0        |
| PC           | 192.168.1.102     | 255.255.255.0        |

`nmtui` can be run from the command line in Ubuntu to configure the network settings of the ethernet connection. Some important settings to note are:
1. Set IPv4 configuration to “Manual” and enter the expected PC IP address and subnet mask
1. Enable the option “Never use this network for default route” (This prevents the PC from attempting to connect to the internet using this port)
1. Enable “Require IPv4 addressing for this connection”
1. Set IPv6 configuration to “Ignore”

## ROS 2 Driver

Consult the github readme for instructions on how to install the ROS 2 driver. The Livox HAP also features an IMU that can be used to help with navigation. Software packages such as `robot_localization` can be configured to take in this IMU data to help improve odometry accuracy.

----

[https://www.livoxtech.com/hap]: https://www.livoxtech.com/hap
[https://github.com/Livox-SDK/livox_ros_driver2]: https://github.com/Livox-SDK/livox_ros_driver2
[https://terra-1-g.djicdn.com/65c028cd298f4669a7f0e40e50ba1131/Livox%20HAP%20(TX)%20User%20Manual.pdf]: https://terra-1-g.djicdn.com/65c028cd298f4669a7f0e40e50ba1131/Livox%20HAP%20(TX)%20User%20Manual.pdf
