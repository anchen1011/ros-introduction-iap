# ros-introduction-iap
For MIT IAP class 2016-2017 (organized under SIPB IAP)

## Baiscs
### install ROS
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

### build your workspace
0. stay with the same terminal
1. `mkdir -p ~/catkin_ws/src`
2. `cd ~/catkin_ws/src`

### compile your workspace (though it is empty by now)
0. stay with the same terminal
1. `cd ~/catkin_ws/`
2. `catkin_make`
3. `source devel/setup.bash` every time before you work under this workspace

### basic commands
0. stay with the same terminal
1. `rospack find [pkg]` e.g. `rospack find roscpp`
2. `roscd [pkg/subdir]` e.g. `roscd rospy` or `roscd rospy/cmake`
3. `rosls [pkg/subdir]` e.g. `rosls rospy` or `rosls rospy/cmake`
4. `rosed [pkg] [filename]` editor by default is vim. switch to emacs, for example, with `export EDITOR='emacs -nw'`   
we'll talk about rosed later

### create your package
0. stay with the same terminal
1. `cd ~/catkin_ws/src`
2. `catkin_create_pkg iap_tutorial std_msgs rospy` [command package-name dependency-1 dependency-2 ...]
3. `cd iap_tutorial`
4. modify package.xml information

## Coding the package
0. stay with the same terminal, cd `cd ~/catkin_ws/src/iap_tutorial`
1. `mkdir include` put includes here
2. `mkdir launch` put launch file here
3. `mkdir msg` put messages here
4. `mkdir src` put c++ source code here
5. `mkdir scripts` put python source code here
6. `mkdir srv` put services here
7. find a proper directory. e.g. `cd ~`
8. `git clone https://github.com/anchen1011/ros-introduction-iap.git` clone this tutorial package. You will see 2 folders inside: sample and exercise. The package inside sample is the complete package for reference, the exercise package is the one we're going to make use to finish this project.
9. There are 6 files in exercise folder. Then I'm going to introduce how each of them works, and how to further code the package.

## Run
0. start a terminal, `roscore`
1. start 2 terminals, do 2-5 for both of them
2. `cd ~/catkin_ws`
3. `. devel/setup.bash`
4. `catkin_make`
5. `catkin_make install`
6. start server with `rosrun iap_tutorial add_two_ints_server.py` in one of the terminal
7. call client in the other terminal `rosrun beginner_tutorials add_two_ints_client.py [x] [y]`   
e.g. `rosrun beginner_tutorials add_two_ints_client.py 4 5`
