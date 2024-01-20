
Sensor Suite
============

Interchagable Payload Unit
--------------------------
Sensing suite is desinged as an interchagable playload unit between **Bell 412 Advanced Research Systems Aircraft (ASRA)** 
and **DJI M600 hexacopter drone** platforms. The payload unit is capable of running visual-inertial-LiDAR odometery and 
mapping algorithms real-time while collecting data. 

.. image:: /images/payload.jpg
   :width: 50%
.. image:: /images/platforms.jpg
   :width: 49%

Sensors
-------

.. .. figure:: /images/platforms.jpg
..       :width: 99%
..       :align: center
..       :alt: Caption for first image

..       The payload is interchagably mounted between **Bell 412 Advanced Research Systems Aircraft (ASRA)** 
..       and a **DJI M600 hexacopter drone**. 

IMU
+++++++++++++++++++++++++++++++
The IMU publish the following ROS topics. 

.. csv-table:: 
   :header: Message Type, Topic Name, Rate [Hz], Description
   :widths: 20,20,20,20
   
   sensor msgs/Imu, /imu/data, 400, raw data
   sensor msgs/Imu, /imu/data stamped, 400, raw data with trigger hardware timestamp 
   geometry msgs/Vector3Stamped, /imu/mag, 100, raw magnetometer data
   sensor msgs/TimeReference, /imu/time_ref, 400,  hardware timestamp at IMU trigger 
   sensor msgs/TimeReference, /imu/time_ref_cam, 20, hardware timestamp at camera trigger
   sensor msgs/TimeReference, /imu/time_ref_pps, 1, hardware timestamp at PPS receive

Cameras
++++++++
The two cameras are publising the following ROS topics.

.. csv-table:: 
   :header: Message Type, Topic Name, Rate [Hz], Description
   :widths: 20,20,20,20
   
   sensor msgs/Image, /camera/image_mono, 20, Mono8 format down camera image
   sensor msgs/Image, /camera/image_color, 20 , RGB8 format down camera image
   sensor msgs/Image, /front_camera/image_mono, 20, Mono8 format front camera image 
   sensor msgs/Image, /front_camera/image_color, 20, RGB8 format front camera image 

LiDAR
++++++++
LiDAR publish the following ROS topics.

.. csv-table:: 
   :header: Message Type, Topic Name, Rate [Hz], Description
   :widths: 20,20,20,20
   
   sensor msgs/PointCloud2, /velodyne_points, 10Hz, raw velodyne pointcloud
   sensor msgs/TimeReference,  /time_ref_scan, 10Hz, hardware timestamp at pcd trigger


GNSS Receriver
++++++++++++++
GNSS module publishes the following ROS topics.

.. csv-table:: 
   :header: Message Type, Topic Name, Rate [Hz], Description
   :widths: 20,20,20,20
   
   sensor msgs/NavSatFix, /fix, 5, raw RTK-GNSS 
   sensor msgs/NavSatFix, /fix_ppk, 5 , PPK GNSS 
   nmea msgs/Sentence, /nmea_sentence, 5, nmea formatted GNSS 
   nav msgs/Odometry, /fix_frl, 5, 6DOF pose ground-truth 

GNSS Base Station
+++++++++++++++++
Reach RS2 Based station is used during data capture. The real-time NMEA stream for the simpleRTK2B was provided by Reach RS2 base station.
RS2 communicates with the ZED-F9P using a ultra high frequncy (UHF) LoRa radio. 
The Reach RS2 also provides a post processed kinematics (PPK) solution upto 100km by logging data at 10Hz.

Jetson Xavier AGX GPU
---------------------
The Xavier is running on Ubuntu 18.04 and NVIDIA L4T 32.3.1 with Cuda 10.1 support, and ROS Melodic is installed on it. 
Additionally, the Xavier board is equipped with a 1GB SSD to store the ROS bags and a Wi-Fi module for data visualization purposes.

Hardware Time-Synchronization Scheme
------------------------------------
The IMU publishes a :math:`/imu/time\_ref` topic, including
the hardware timestamp of the IMU's internal clock for the
published data. The point cloud acquisition hardware time
and the camera trigger pulse hardware timestamp are pub-
lished on :math:`/time\_ref\_scan`` and :math:`/imu/time\_ref\_cam``
topics, respectively. The timestamp of the received PPS
message from the GNSS receiver is published on the
:math:`/imu/time\_ref\_pps`` topic. These hardware timestamps
can be used to accurately time-sync sensor messages. The
block diagram of the hardware synchronization is shown below.

.. image:: /images/sync.svg
   :width: 50%

