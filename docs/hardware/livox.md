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

The Livox HAP connects to the PC via an ethernet cable. The network settings on the PC must be properly configured to successfully communicate with the LiDAR sensor. The default IP address for the sensor and PC can be found in the table below (taken from the default config values from the ROS driver, double check your livox_ros_driver2/config/HAP_config.json)

| Device       | Default IP        |
|:-------------|:------------------|
| Livox HAP    | 192.168.1.100     |
| PC           | 192.168.1.50      |

`nmtui` can be run from the command line in Ubuntu to configure the network settings of the ethernet connection. Some important settings to note are:
1. Set IPv4 configuration to “Manual” and enter the expected PC IP address
1. Enable the option “Never use this network for default route” (This prevents the PC from attempting to connect to the internet using this port)
1. Enable “Require IPv4 addressing for this connection”
1. Set IPv6 configuration to “Ignore”
1. Use `ifconfig` to double check that the changes were applied. Deactivate/Activate the connection or reboot the PC to apply the changes

## ROS 2 Driver

Consult the github readme for instructions on how to install the ROS 2 driver. If you encounter shared library errors with the ROS2 driver, with Ubuntu 22.04 the Livox-SDK2 shared library will be installed to the wrong location and the ROS driver will be unable to find it. Move all liblivox files from "/usr/local/lib" to "/usr/lib", you will need sudo privileges to do this. Any changes made to the launch files will require recompiling the workspace using the provided build.sh script

The Livox HAP also features an IMU that can be used to help with navigation. Software packages such as `robot_localization` can be configured to take in this IMU data to help improve odometry accuracy.

----

[https://www.livoxtech.com/hap]: https://www.livoxtech.com/hap
[https://github.com/Livox-SDK/livox_ros_driver2]: https://github.com/Livox-SDK/livox_ros_driver2
[https://terra-1-g.djicdn.com/65c028cd298f4669a7f0e40e50ba1131/Livox%20HAP%20(TX)%20User%20Manual.pdf]: https://terra-1-g.djicdn.com/65c028cd298f4669a7f0e40e50ba1131/Livox%20HAP%20(TX)%20User%20Manual.pdf
