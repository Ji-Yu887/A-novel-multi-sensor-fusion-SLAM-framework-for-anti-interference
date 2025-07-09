A novel multi-sensor fusion SLAM framework for anti-interference

Dataset (db source file, 3D point cloud, comparison results, pictures)address:https://drive.google.com/drive/folders/1jgLQR9aIeaogL5X3IKGdqV7ztY4HppG2

Experimental scene video address: https://www.youtube.com/playlist?list=PLOXGzqGWQxHYm6_UVJ4UMLaBPIlK_MDrj

We do not provide smart car hardware or any sensor configuration files. Researchers can modify their systems based on their own smart car hardware.

For code description, we provide the code of clahe, lidar noise and timestamp synchronization files. For the RTAB-Map source code, please refer to the github repository of the RTAB-Map author.

The recommendation for researchers who want to reproduce our paper is to change the topic mapping in the RGB-D configuration file in the RTAB-Map project and any configuration file involving sensors to the enhanced topic names.

Environment requirements: ROS2 Foxy + Ubuntu 20.04 + OpenCV4.5 + RTAB-Map_ros

## Acknowledgements
Part of the LiDAR filtering module is adapted from: [ch-geo/lidar_noise_filtering](https://github.com/ch-geo/lidar_noise_filtering) (MIT License).
