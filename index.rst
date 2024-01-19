.. MUN-FRL Dataset documentation master file, created by
   sphinx-quickstart on Sat Oct 15 14:42:58 2022.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

MUN-FRL: Aerial Visual-Inertial-LiDAR Odometry and Mapping Dataset 
===================================================================

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
global navigation system (GNSS) receiver and a Jetson AGX Xavier GPU as processing unit.
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
   :header: Dataset,Size [GB],Length [m],Duration [s],ROS bag
   :widths: 20,10,10,10,10
   
   quarry1,27.2,357,231, `link <https://drive.google.com/drive/folders/1-cN8PKBhh5REuKsP69V0s5cf-PcBO_eR?usp=sharing>`_
   quarry2,79.8,807,675, `link <https://drive.google.com/drive/folders/1flDXDGoUXpRpQisJcKXBH-tTqEwC6UZg?usp=sharing>`_
   lighthouse,89.9,890,756, `link <https://drive.google.com/drive/folders/1TzMhbG5N4v6L8JeI1XPaw9YCpwuj8jbI?usp=sharing>`_ 
   bell412_dataset1,45.9,1709,432, `link <https://drive.google.com/drive/folders/18jG0_auUzMB6SNq_xTYDs2vzMYAebGIc?usp=sharing>`_
   bell412_dataset2,45.8,x,436, `link <https://drive.google.com/drive/folders/1gql9_Wydn7Kyc7hC6V8BFugDDbYJgsTt?usp=sharing>`_
   bell412_dataset3,32.2,4336,308, `link <https://drive.google.com/drive/folders/1CbSIJEn9XPw4c0HJrn3_gIDifTR6rhLx?usp=sharing>`_
   bell412_dataset4,33.0,3656,316, `link <https://drive.google.com/drive/folders/1MjBBT7bxMADMQE5r0wTlVj4p17yT6Gjg?usp=sharing>`_
   bell412_dataset5,34.1,2138,483, `link <https://drive.google.com/drive/folders/1tBHKwTXkFQTpK57eI5ySmqV6iw8SHFg5?usp=sharing>`_
   bell412_dataset6,47.6,4938,520, `link <https://drive.google.com/drive/folders/1FONJtovVx__3iLLVI_ET8yheDF9-ZWqG?usp=sharing>`_

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