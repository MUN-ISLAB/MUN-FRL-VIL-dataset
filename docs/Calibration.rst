Sensor Calibration
==================
To assist in explaining the calibration process presented in this section, 
the hardware measurements and schematic of the coordinate system transformations are provided below.

.. image:: /images/side_ann.svg
   :width: 50%
.. image:: /images/tf.svg
   :width: 49%

Camera Intrinsic Calibration
----------------------------
The intrinsic parameters of the cameras, such as the camera model, camera matrix [K], and distortion parameters, 
were obtained using the camera calibration tool that is included in the VINS-Fusion package. 
The values obtained are presented below.

.. :math:`\begin{aligned}
.. & K = \begin{bmatrix}
.. a_{11} & a_{12} & a_{13} \\
.. a_{21} & a_{22} & a_{23} \\
.. a_{31} & a_{32} & a_{33}
.. \end{bmatrix} \\
.. &\text{This is some text below the matrix.}
.. \end{aligned}`

For Bell412 Datasets: 

.. literalinclude:: /images/cam_intrinsic_bell412.yaml
    :language: yaml

For DJI M600 Datasets:

.. literalinclude:: /images/cam_intrinsic_m600.yaml
    :language: yaml

IMU Intrinsic Calibration
-------------------------
The IMU parameters for both Bell412 and DJI M600 datasets are given below. 

.. literalinclude:: /images/imu_prams.yaml
    :language: yaml


Camera-IMU Extrinsic Calibration
--------------------------------
The camera-IMU transformation was found using Kalibr package.

For Bell412 Datasets: 

The down camera :math:`T_{BCd}` and front camera :math:`T_{BCf}`

.. literalinclude:: /images/T_BC_bell412.yaml
    :language: yaml

For DJI M600 Datasets:

The down camera :math:`T_{BCd}` and front camera :math:`T_{BCf}`

 .. literalinclude:: /images/T_BC_m600.yaml
    :language: yaml

Camera-LiDAR Extrinsic Calibration
----------------------------------
Down camera to LiDAR transfromation :math:`[T_{CLd}]` was found using Matlab LiDAR calibrator toolbox
and fine-tuned using manual realignment. 

For Bell412 datasets:

.. literalinclude:: /images/T_CL_bell412.yaml
    :language: yaml

For DJI M600 datasets: 

.. literalinclude:: /images/T_CL_m600.yaml
    :language: yaml

IMU-GNSS Extrinsic Calibration
------------------------------
IMU to GNSS transformation :math:`[T_{BG}]` for both Bell412 and DJI M600 datasets are given here. 

.. literalinclude:: /images/T_BG.yaml
    :language: yaml
