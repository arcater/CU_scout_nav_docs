---
title: Jetson AGX Orin
parent: Hardware 
nav_order: 5
---

# Jetson AGX Orin Developer kit

Jetson Orin Product Page:
[https://www.nvidia.com/en-us/autonomous-machines/embedded-systems/jetson-orin/]

User Guide:
[https://developer.nvidia.com/embedded/learn/jetson-agx-orin-devkit-user-guide/index.html]

Jetson Linux Archive:
[https://developer.nvidia.com/embedded/jetson-linux-archive]

## Flashing the Jetson

The package manager for the Jetson can be fragile at times. Encountering 'broken packages' when attempting to install new packages can be a common occurrence. If the Jetson Linux install is broken beyond repair, it is necessary to re-flash the Jetson to return it to working order.

I would recommend attempting to flash the latest version of Jetson Linux that is compatible with the AGX Orin. Ensure that the version of Ubuntu is compatible with your target ROS distribution (or a docker container could be used as a workaround). Navigate to the Jetson Linux archive, select a version, and navigate to the developer guide for flashing instructions.

Consult this pdf file for instructions on how to flash Jetson Linux 36.3 with a virtual machine:
[https://github.com/RowanW09/AgileX_Autonomous_Driving_CU_Summer_2024/blob/Summer-2025/Readme.pdf]

----

[https://www.nvidia.com/en-us/autonomous-machines/embedded-systems/jetson-orin/]: https://www.nvidia.com/en-us/autonomous-machines/embedded-systems/jetson-orin/
[https://developer.nvidia.com/embedded/learn/jetson-agx-orin-devkit-user-guide/index.html]: https://developer.nvidia.com/embedded/learn/jetson-agx-orin-devkit-user-guide/index.html
[https://developer.nvidia.com/embedded/jetson-linux-archive]: https://developer.nvidia.com/embedded/jetson-linux-archive
[https://github.com/RowanW09/AgileX_Autonomous_Driving_CU_Summer_2024/blob/Summer-2025/Readme.pdf]: https://github.com/RowanW09/AgileX_Autonomous_Driving_CU_Summer_2024/blob/Summer-2025/Readme.pdf
