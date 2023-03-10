.. MUN-FRL Dataset documentation master file, created by
   sphinx-quickstart on Sat Oct 15 14:42:58 2022.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

MUN-FRL: Aerial Visual-Inertial-LiDAR Odometry and Mapping Dataset 
===========================================================================

.. image:: /images/pl1.jpg
   :width: 23%
.. image:: /images/pl_v1.png
   :width: 35%
.. image:: /images/LH_m600_flight_cp.png
   :width: 39%
.. image:: /images/bell_1_map.jpg
   :width: 98%

This webpage presents the visual-inertial-LiDAR (VIL) datasets collected by an interchagable payload unit atttached to 
a Bell 412 Advanced Systems Research Helicopter (ASRA) helicoptor and a DJI M600 hexacoptor drone.
The payload unit consists of two monocular global shutter cameras, a 3D LiDAR, an IMU, real-time kinematic (RTK) enabled 
global navigation system (GNSS) receiver and a Jetson AGX Xavier GPU.
The two cameras, IMU, LiDAR and GNSS receivers are hardware time-synchronized.

Available Data
--------------
Images
++++++
* FLIR BFS-U3-16S2M-BD - Nadir view [global shutter, 1140x1080, monochrome (Mono8) and color (RGB8), 20Hz]
* FLIR BFS-PGE-04S2C-CS - Forward view [global shutter, 720x540, monochrome (Mono8) and color (RGB8), 20Hz]
  
IMU Measurements
++++++++++++++++
* Xsens MTi-30 IMU - [angular rate, accleration - 400Hz, magnetic field - 100Hz]

Pointclouds
+++++++++++
* Velodyne VLP-16 LiDAR - Downward facing [pointclouds, 360° horizontal, 30° vertical FOV, 10Hz] 

Ground-Truth
++++++++++++
* simpleRTK2B RTK-GNSS receriver - [3D position, 5Hz]
* Post processed kenematic (PPK) ground truth - [3D position, 5Hz]



Downloads 
---------
.. csv-table:: 
   :header: Dataset name,Size [GB],Length [m],Duration [s],ROS bag
   :widths: 20,10,10,10,10
   
   quarry1,27.2,357,231,link
   quarry2,79.8,807,675,link
   lighthouse,89.9,890,756,link 
   bell412_dataset1,45.9,1709,432,link
   bell412_dataset2,45.8,x,436,link
   bell412_dataset3,32.2,4336,308,link
   bell412_dataset4,33.0,3656,316,link
   bell412_dataset5,34.1,2138,483,link
   bell412_dataset6,47.6,4938,520,link

Notes 
-----

Lisence
-------
   


.. toctree::
   :maxdepth: 2
   :hidden:
   :caption: Dataset Overview

   sensors
   Calibration
   ground truth