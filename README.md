# <ros_web_teleop>
A ROS Web  Keyboard control. Based with robotwebtools.

ROSWeb is a web based supervisory system for Robot Operating System (ROS).

It is a web application that manages robots on a single web page.

# How to use

As ROSWeb is a tool for ROS, it depends on a machine running the roscore process. It is a web application and it depends on websockets provided by rosbridge server. Until now, it is being developed and tested using Google Chrome browser.

1.Install RosbridgeSuite package and WebVideoServer

'''
$ sudo apt-get update
$ sudo apt-get install ros-indigo-rosbridge-suite
$ sudo apt-get install ros-indigo-web-video-server
'''

2.Install dependencies

'''
$ rosdep update  
# Do NOT run rosdep update with sudo. It is not required and will result in permission errors later on. 
$ rosdep install rosbridge_server
$ rosdep install web_video_server
or $ rosdep install --from-paths src --ignore-src -r -y  
# installs all the packages that the packages in your catkin workspace depend upon
'''

3.Install latest development version of rosbrige_server 

'''
$ cd catkin_ws/src/
$ git clone -b develop https://github.com/RobotWebTools/rosbridge_suite.git
$ git clone https://github.com/sun-coke/ros_web_teleop.git
$ cd.. && catkin_make

4.Run

'''
$ roslaunch turtlebot3_gazebo turtlebot3_empty_world.launch 
$ roslaunch rosbridge_server rosbridge_websocket.launch
$ rosrun web_video_server web_video_server
$ cd catkin_ws/src/ros_web_teleop 
# open the keyboardteleop.html using Google Chrome browser.and using W、A、S、D to control the robot.
'''



