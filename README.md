# ros-introduction-iap
For MIT IAP class 2016-2017 (organized under SIPB IAP)

## install ROS
1. open a terminal
2. `sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'`
3. `sudo apt-key adv --keyserver hkp://pool.sks-keyservers.net --recv-key 421C365BD9FF1F717815A3895523BAEEB01FA116`
4. `sudo apt-get update`
5. `sudo apt-get install ros-jade-desktop-full` it takes around 4.4 minutes
6. `sudo rosdep init`
7. `rosdep update`
8. **[optional]** `echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc`
9. **[if you've done 8.]** `source ~/.bashrc` **[if not]** `source /opt/ros/jade/setup.bash`
10. `sudo apt-get install python-rosinstall`

## build your workspace
0. stay with the same terminal
1. `mkdir -p ~/catkin_ws/src`
2. `cd ~/catkin_ws/src`

## compile your workspace (though it is empty by now)
0. stay with the same terminal
1. `cd ~/catkin_ws/`
2. `catkin_make`
3. `source devel/setup.bash` every time before you work under this workspace

## basic commands
0. stay with the same terminal
1. `rospack find [pkg]` e.g. `rospack find roscpp`
2. `roscd [pkg/subdir]` e.g. `roscd rospy` or `roscd rospy/cmake`
3. `rosls [pkg/subdir]` e.g. `rosls rospy` or `rosls rospy/cmake`

## create your package
0. stay with the same terminal
1. `cd ~/catkin_ws/src`
2. `catkin_create_pkg iap_tutorial std_msgs rospy` [command package-name dependency-1 dependency-2 ...]
3. `cd iap_tutorial`
4. modify package.xml information
