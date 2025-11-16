---
title: Hikrobot Camera
parent: Hardware 
nav_order: 31
---

# Hikrobot RGB Camera

Model Number:
MV-CE060-10UC

Product page:
[https://www.hikrobotics.com/en/machinevision/productdetail/?id=7686]

Spec sheet:
[https://www.maxxvision.com/downloads/Cameras/USB30/Hikrobot/Hikrobot_MV-CE060-10UMUC.pdf]

ROS2 driver:
[https://github.com/FraunhoferIOSB/camera_aravis2]

## Camera tools

Aravis tools can be used to display the camera feed to a desktop GUI application. You may need to enable settings such as auto-exposure or remove the lens cap to get an actual picture from the camera. The focus of the camera lens can be physically adjusted as well.

```bash
sudo apt install aravis-tools
sudo apt install aravis-tools-cli
arv-viewer-0.8
```

## Debugging

If you run into permission issues or your camera is not appearing in arv-viewer even though it is plugged in, you may need to change the USB device permissions.

The following tutorial can help solve this issue:
[https://www.xmodulo.com/change-usb-device-permission-linux.html]

Some commands that may help with this:
```bash
sudo lshw
sudo lsusb -vvv
sudo gedit /etc/udev/rules.d/50-camusb.rules
```

## ROS2 Driver

ROS2 driver:
[https://github.com/FraunhoferIOSB/camera_aravis2]

Installation instructions for camera_aravis2 can be found in the readme, as well as example launch and config files.

```bash
ros2 launch hik_camera_driver.py
```

ROS2 Image sensor_msg header data excerpt:
```yaml
header:
  frame_id: camera_uv_vis
height: 2048
width: 3072
encoding: bayer_rggb8
is_bigendian: 0
step: 3072
```

----

[https://www.hikrobotics.com/en/machinevision/productdetail/?id=7686]: https://www.hikrobotics.com/en/machinevision/productdetail/?id=7686
[https://www.maxxvision.com/downloads/Cameras/USB30/Hikrobot/Hikrobot_MV-CE060-10UMUC.pdf]: https://www.maxxvision.com/downloads/Cameras/USB30/Hikrobot/Hikrobot_MV-CE060-10UMUC.pdf
[https://github.com/FraunhoferIOSB/camera_aravis2]: https://github.com/FraunhoferIOSB/camera_aravis2
[https://www.xmodulo.com/change-usb-device-permission-linux.html]: https://www.xmodulo.com/change-usb-device-permission-linux.html
