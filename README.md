# simple_robot_custom_ctlr

This ROS package provides a slice step up on the simple_robot model, by removing the differential drive controller, and replacing it with two velocity controllers for the two wheels.  It provides a suitable template for students to test the knowledge of mobile robot kinematics, to replicate the differential drive controller.

Included in the package are:
* Package.xml and CMakeLists.txt files
* a xacro and gazebo file, enhanced slightly from the simple_robot package to include different colors for each wheel, in order to allow easier debugging from RVIZ.  Additionally the appropriate velocity controllers are appied inside the gazebo file.
* a world file for gazebo with moveable walls.
* a config file for the velocity controllers
* a launch file for Gazebo and Rviz
* a config file for Rviz

To test the Package, start the launch file, see that no errors appear in the command window while starting Gazebo and then in a second terminal window, send a command to one of the velocity controllers with:

rostopic pub wheel_left_velocity_controller/command std_msgs/Float64 -- '0.5'

or 

rostopic pub wheel_right_velocity_controller/command std_msgs/Float64 -- '0.5'
