# ros-introduction-iap
For MIT IAP class 2016-2017 (organized under SIPB IAP)

## installation
1. open a terminal
2. `sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'`
3. `sudo apt-key adv --keyserver hkp://pool.sks-keyservers.net --recv-key 421C365BD9FF1F717815A3895523BAEEB01FA116`
4. `sudo apt-get update`
5. `sudo apt-get install ros-jade-desktop-full` it takes around 4.4 minutes
6. `sudo rosdep init`
7. `rosdep update`
8. [optional] `echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc`
9. *[if you've done 8.]* `source ~/.bashrc` 

*[if not (do this every time you open a terminal to work on ROS)]* `source /opt/ros/jade/setup.bash`
10. 
