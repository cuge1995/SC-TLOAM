# SC-TLOAM

## What is SC-TLOAM? 
- A real-time LiDAR SLAM package that integrates TLOAM and ScanContext. 
    - **TLOAM** for odometry.
    - **ScanContext** for coarse global localization that can deal with big drifts (i.e., place recognition as kidnapped robot problem without initial pose)
    - and iSAM2 of GTSAM is used for pose-graph optimization. 

## Dependencies
- We mainly depend on ROS, Ceres and Open3D(for TLOAM), and GTSAM (for pose-graph optimization). 
    - For the details to install the prerequisites, please follow the TLOAM and LIO-SAM repositiory. 
- The below examples are done under ROS melodic (ubuntu 18) and GTSAM version 4.x. 

## How to use? 
- First, install the abovementioned dependencies, and follow below lines. 
```
    mkdir -p ~/catkin_scTLOAM_ws/src
    cd ~/catkin_scTLOAM_ws/src
    git clone https://github.com/cuge1995/SC-TLOAM.git
    cd ../
    catkin_make
    source ~/catkin_scTLOAM_ws/devel/setup.bash
```

## Example Results 


### KITTI 
- For KITTI (HDL-64 sensor), run using the command (Download [KITTI sequence 05](https://drive.google.com/file/d/1eyO0Io3lX2z-yYsfGHawMKZa5Z0uYJ0W/view?usp=sharing) or [KITTI sequence 07](https://drive.google.com/file/d/1_qUfwUw88rEKitUpt1kjswv7Cv4GPs0b/view?usp=sharing) first)
    ```
    ##In different terminal
    roslaunch tloam tloam_kitti.launch
    roslaunch aloam_velodyne tloam_velodyne_64.launch
    rosbag play 2011_09_30_0018.bag
    ```


## Acknowledgements
- Thanks to LOAM, TLOAM, SC-ALOAM and LIO-SAM code authors. The major codes in this repository are borrowed from their efforts.

