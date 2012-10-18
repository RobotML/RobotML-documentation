Standard sensors structures
---------------------------

*Lidar 1 layer:*
^^^^^^^^^^^^^^^^

Stereotype LidarSystem
1 output port => LaserScan ROS datatype
http://www.ros.org/doc/api/sensor_msgs/html/msg/LaserScan.html

*Lidar N layers:*
^^^^^^^^^^^^^^^^^

Stereotype LidarSystem
MultiLaserScan (based on the structure LaserScan ROS datatype)
Note: This model can fit all lidars, whether single or multi-layers

MultiLaserScan structure content:

header header
layer_angle_min float32;
layer_angle_max float32;
layer_angle_increment float32;
LaserScan [] layers;

*Camera:*
^^^^^^^^^

Stereotype CameraSystem
1 output port => Image ROS datatype
http://www.ros.org/doc/api/sensor_msgs/html/msg/Image.html

*Stereovision camera:*
^^^^^^^^^^^^^^^^^^^^^^

Stereotype CameraSystem
1 output port => Image ROS datatype for the left image
1 output port => Image ROS datatype for right image

*GPS:*
^^^^^^

Stereotype GPSSystem
1 output port => NavSatFix
http://www.ros.org/doc/api/sensor_msgs/html/msg/NavSatFix.html

*IMU:*
^^^^^^

Stereotype IMUSystem
1 output port => Imu ROS datatype
http://www.ros.org/doc/api/sensor_msgs/html/msg/Imu.html

*INS (Inertial Navigation System):*
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Stereotype INSSystem
Port 1 output: NavSatFix ROS datatype
Port 1 output: Imu ROS datatype
(for Landins Vipalab sensor, for example)

*IR sensor proximetry:*
^^^^^^^^^^^^^^^^^^^^^^^

Port 1 output: Range ROS datatype
http://www.ros.org/doc/api/sensor_msgs/html/msg/Range.html

*Vehicles:*
^^^^^^^^^^^

- CarLikeVehicle: vehicle with one wheel steering

Stereotype CarLikeVehicleSystem
1 output port => CarLikeOdometry

CarLikeOdometry structure content :

Header header
    uint32 seq = numbering from 0 and is incremented for each message
    time stamp
float64 steering_angle;
float64 velocity;
float64 left_rear_wheel_velocity;
float64 right_rear_wheel_velocity;


- DifferencialVehicle: vehicle with 2 wheels (tank like vehicle)

Stereotype DifferencialVehicleSystem
1 output port => DifferencialOdometry

DifferencialOdometry structure content :
Header header
    uint32 seq = numbering from 0 and is incremented for each message
    time stamp
float64 left_distance;
float64 right_distance;
float64 left_velocity;
float64 right_velocity;

TBD
