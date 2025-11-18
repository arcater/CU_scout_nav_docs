---
title: Robosense Helios-16P
parent: Hardware 
nav_order: 10
---

# Robosense Helios-16P

Manufacturer site:
[https://www.robosense.ai/en/rslidar/RS-Helios]

rslidar_SDK:
[https://github.com/RoboSense-LiDAR/rslidar_sdk]

Link to Helios 16P user manual (3rd party site):
[https://cdn-reichelt.de/documents/datenblatt/C900/RS-HELIOS-16P_USER_GUIDE_V1.0.1_EN.pdf]

## Configuration

The Robosense Helios-16P connects to the PC via an ethernet cable. The network settings on the PC must be properly configured to successfully communicate with the LiDAR sensor. The default IP addresses for the sensor and PC can be found in the table below (taken from Helios-16P manual).

| Device       | Default IP        |
|:-------------|:------------------|
| Helios-16P   | 192.168.1.200     |
| PC           | 192.168.1.102     |

`nmtui` can be run from the command line in Ubuntu to configure the network settings of the ethernet connection. Some important settings to note are:
1. Set IPv4 configuration to “Manual” and enter the expected PC IP address
1. Enable the option “Never use this network for default route” (This prevents the PC from attempting to connect to the internet using this port)
1. Enable “Require IPv4 addressing for this connection”
1. Set IPv6 configuration to “Ignore”
1. Use `ifconfig` to double check that the changes were applied. Deactivate/Activate the connection or reboot the PC to apply the changes

## Web Interface & Debugging

The Helios-16P features a web interface that can be loaded from a web browser by typing in the IP address of the LiDAR sensor. From here various settings for the LiDAR sensor can be configured. This web interface is useful as a method to confirm successful communication between the LiDAR sensor and the PC. If this web interface does not load, then debugging is required. Ensure that the LiDAR is properly powered and connected to the PC. Programs such as `wireshark` can be used to analyze the messages coming from the LiDAR sensor to determine the IP of the sensor and the expected PC IP.

## ROS SDK

Documentation for how to install the SDK can be found in the readme of the SDK’s github. Once the SDK is installed, it is necessary to modify the config.yaml file present in the src directory of the workspace. From this config file you must specify the name of your Robosense LiDAR model. For our purposes ensure that the output point cloud option is enabled. The name of the output topic and frame link can also be modified here if needed.

Once everything is configured and the SDK is installed, the following command can be run to publish the point cloud data and visualize the output in RVIZ

```bash
ros2 launch rslidar_sdk start.py
```

----

[https://www.robosense.ai/en/rslidar/RS-Helios]: https://www.robosense.ai/en/rslidar/RS-Helios
[https://github.com/RoboSense-LiDAR/rslidar_sdk]: https://github.com/RoboSense-LiDAR/rslidar_sdk
[https://cdn-reichelt.de/documents/datenblatt/C900/RS-HELIOS-16P_USER_GUIDE_V1.0.1_EN.pdf]: https://cdn-reichelt.de/documents/datenblatt/C900/RS-HELIOS-16P_USER_GUIDE_V1.0.1_EN.pdf
