nmea_navsat_driver
===============

ROS driver to parse NMEA strings and publish standard ROS NavSat message types. Does not require the GPSD daemon to be running.

API
---

This package has no released Code API.

The ROS API documentation and other information can be found at http://ros.org/wiki/nmea_navsat_driver


More information:
http://wiki.ros.org/nmea_navsat_driver



Installation
------------

$ cd catkin_ws/src

$ git clone https://github.com/ros-agriculture/nmea_navsat_driver.git

$ cd ..

From ~/catkin_ws, $ catkin_make

$ source devel/setup.bash


Running
---------

Example launch file:  https://github.com/ros-agriculture/nmea_navsat_driver/blob/master/launch/nmea_serial_driver.launch
Tutorial on launch files: https://www.youtube.com/watch?v=pCBwos89fI0


These are generally the parameters that need to be configured.
  <arg name="port" default="/dev/ttyUSB0" />
  
  <arg name="baud" default="4800" />
  
  
There are three nodes in this package

nmea_topic_driver
NMEA GPS Topic driver node. Reads NMEA sentences from a ROS topic instead of directly from e.g. a serial port.
http://wiki.ros.org/nmea_navsat_driver#nmea_topic_driver


nmea_serial_driver
NMEA GPS Serial driver node. Replaces nmea_gps_driver.py to reduce naming conflicts and use new common parsing+driver backend.
http://wiki.ros.org/nmea_navsat_driver#nmea_serial_driver 


nmea_topic_serial_reader
Reads NMEA sentences from the specified serial port and publishes them to a ROS topic. This is a simple front-end for use with nmea_topic_driver.py
http://wiki.ros.org/nmea_navsat_driver#nmea_topic_serial_reader
