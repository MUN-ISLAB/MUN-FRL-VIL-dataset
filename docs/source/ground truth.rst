Ground-Truth Data 
=================

A real-time kinematic (RTK) capable GNSS receiver with a GNSS base station is used as 
the ground-truth source for the dataset.

SimpleRTK2B board is used as the GNSS receiver that has an u-blox ZED-F9P multi-band receiver module with multiple 
constellations support. The RTK module inside the ZED-F9P has the capability of providing 
the receivers location at an accuracy of 1cm in open environments.

The real-time NMEA stream for the ZED-F9P was provided by Reach RS2 base station. 
RS2 communicates with the ZED-F9P using a ultra high frequncy (UHF) LoRa radio.
The Reach RS2 also capable of providing a post processed kinematics (PPK) solution upto 100km by logging data at 10Hz.

.. image:: /images/rtk_image.png
   :width: 50%

Ground-Truth Sources
++++++++++++++++++++

* Raw ROS Topics

.. csv-table:: 
   :header: Message Type, Topic Name, Rate [Hz], Description
   :widths: 20,20,20,20
   
   sensor msgs/NavSatFix, /fix, 5, raw RTK-GNSS 
   nmea msgs/Sentence, /nmea_sentence, 5, nmea formatted RTK-GNSS

* Post processed ROS Topics - Higher accuracy than raw RTK-GNSS Measuremnts
  
.. csv-table:: 
   :header: Message Type, Topic Name, Rate [Hz], Description
   :widths: 20,20,20,20
   
   sensor msgs/NavSatFix, /fix_ppk, 5 , PPK GNSS 
   nav msgs/Odometry, /fix_frl, 5, 6DOF pose ground-truth

.. * CSV files
  
.. .. csv-table:: 
..    :header: Message Type, Topic Name, Rate [Hz], Description
..    :widths: 20,20,20,20
   
..    sensor msgs/NavSatFix, /fix_ppk, 5 , PPK GNSS 
..    nav msgs/Odometry, /fix_frl, 5, 6DOF pose ground-truth
  

