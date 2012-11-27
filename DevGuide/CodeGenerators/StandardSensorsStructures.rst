Standard sensors structures
---------------------------

*Lidar 1 layer:*
^^^^^^^^^^^^^^^^

* Stereotype LidarSystem
* 1 output port:

  * LaserScan ROS datatype http://www.ros.org/doc/api/sensor_msgs/html/msg/LaserScan.html

*Lidar N layers:*
^^^^^^^^^^^^^^^^^

This model can fit all lidars, whether single or multi-layers.

* Stereotype LidarSystem
* 1 output port:

  * Datatype MultiLaserScan (based on the structure LaserScan ROS datatype)


* MultiLaserScan structure content:

  * header header
  * layer_angle_min float32;
  * layer_angle_max float32;
  * layer_angle_increment float32;
  * LaserScan [] layers;

*Camera:*
^^^^^^^^^

* Stereotype CameraSystem
* 1 output port:

  * Image ROS datatype http://www.ros.org/doc/api/sensor_msgs/html/msg/Image.html

*Stereovision camera:*
^^^^^^^^^^^^^^^^^^^^^^

* Stereotype CameraSystem
* 2 output ports:

  * Image ROS datatype for the left image
  * Image ROS datatype for right image

*GPS:*
^^^^^^

* Stereotype GPSSystem
* 1 output port:

  * NavSatFix ROS datatype http://www.ros.org/doc/api/sensor_msgs/html/msg/NavSatFix.html

*IMU:*
^^^^^^

* Stereotype IMUSystem
* 1 output port:

  * Imu ROS datatype http://www.ros.org/doc/api/sensor_msgs/html/msg/Imu.html

*INS (Inertial Navigation System):*
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

For Landins Vipalab sensor, for example.

* Stereotype INSSystem
* 2 output ports:

  * NavSatFix ROS datatype http://www.ros.org/doc/api/sensor_msgs/html/msg/NavSatFix.html
  * Imu ROS datatype http://www.ros.org/doc/api/sensor_msgs/html/msg/Imu.html

*IR sensor proximetry:*
^^^^^^^^^^^^^^^^^^^^^^^

* Stereotype IRProximetrySystem
* 1 output port:

  * Range ROS datatype http://www.ros.org/doc/api/sensor_msgs/html/msg/Range.html

*Vehicles:*
^^^^^^^^^^^

Vehicle with one wheel steering (Vipalab, for example).

* Stereotype CarLikeVehicleSystem
* 1 output port:

  * Structure CarLikeOdometry


* CarLikeOdometry structure content:

  * Header header
  * uint32 seq = numbering from 0 and is incremented for each message
  * time stamp
  * float64 steering_angle;
  * float64 velocity;
  * float64 left_rear_wheel_velocity;
  * float64 right_rear_wheel_velocity;

Vehicle with 2 wheels (tank like vehicle)

* Stereotype DifferencialVehicleSystem
* 1 output port

  * Structure DifferencialOdometry


* DifferencialOdometry structure content :

  * Header header
  * uint32 seq = numbering from 0 and is incremented for each message
  * time stamp
  * float64 left_distance;
  * float64 right_distance;
  * float64 left_velocity;
  * float64 right_velocity;

TBD
