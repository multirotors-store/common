# Overview

**Intel® RealSense™ SDK 2.0** is a cross-platform library for Intel® RealSense™ depth cameras.

This document to show how to build and install Intel® RealSense™ SDK 2.0  and the ROS wrapper realsense-ros on the companion Computer (we are using the i.MX8 NavQPlus at the current)

For the Intel RealSense D435i camera working on the i.MX8 NavQPlus, we need to using the combination of **librealsense v2.41.0** and the ROS Wrapper **realsense-ros v2.2.21**

# Companion Computer Configuration

Ideally, you have done the i.MX8 NavQPlus configuration.

Please refer to "Autonomous/IMX8" session.

# Building librealsense

1. Make sure no RealSense device is connected
2. To build the librealsense, navigate to the librealsense directory and run the script:
   ```
   cd autonomous-flight-stack/Material/Realsense/librealsense/
   ./libuvc_installation.sh
   ```
3. Wait until `Librealsense script completed` message is displayed (may take some time)
4. Connect Realsense device (D435i Depth Camera)
5. Run `rs-enumerate-devices` from the terminal to verify the installation

# Building realsense-ros

1. Install the ROS distribution

   We use the the ROS Noetic on Ubuntu 20.04. Please follow the [ROS Noetic](http://wiki.ros.org/noetic/Installation/Ubuntu) guidline
2. Install Intel® RealSense™ ROS from Sources

   - Create a catkin workspace Ubuntu using commands:

     ```
     mkdir -p ~/catkin_ws_realsense_ros/src
     cd ~/catkin_ws_realsense_ros/src/
     ```
   - Clone the Intel® RealSense™ ROS into **catkin_ws_realsense_ros/src/** and checkout to v2.2.21 tag

     ```
     git clone https://github.com/IntelRealSense/realsense-ros.git
     cd realsense-ros/
     git checkout v2.2.21
     cd ..
     ```
   - Make sure all dependent packages are installed. You can check .travis.yml file for reference
   - Specifically, make sure that the ros package ddynamic_reconfigure is installed. Using the command:

     `sudo apt install ros-noetic-ddynamic-reconfigure`
   - Build the realsense-ros with commands:

     ```
     catkin_init_workspace
     cd ..
     catkin_make clean
     catkin_make -DCATKIN_ENABLE_TESTING=False -DCMAKE_BUILD_TYPE=Release
     catkin_make install
     echo "source ~/catkin_ws_realsense_ros/devel/setup.bash" >> ~/.bashrc
     source ~/.bashrc
     ```
