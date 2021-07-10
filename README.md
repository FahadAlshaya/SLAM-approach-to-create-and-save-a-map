# SLAM-approach-to-create-and-save-a-map

i use Ros  Melodic and ubuntu-18.04 to SLAM approach to create and save a map

## Install ROS 1 on Remote PC
- `$ sudo apt update`
- `$ sudo apt upgrade`
- `$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_melodic.sh
`
- `$ chmod 755 ./install_ros_melodic.sh `
- `$ bash ./install_ros_melodic.sh`

## Install Dependent ROS 1 Packages
- `$ sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy \
  ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc \
  ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan \
  ros-melodic-rosserial-arduino ros-melodic-rosserial-python \
  ros-melodic-rosserial-server ros-melodic-rosserial-client \
  ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server \
  ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro \
  ros-melodic-compressed-image-transport ros-melodic-rqt* \
  ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers`
  
  ## Install TurtleBot3 Packages
  - `$ sudo apt-get install ros-melodic-dynamixel-sdk`
  - `$ sudo apt-get install ros-melodic-turtlebot3-msgs`
  - `$ sudo apt-get install ros-melodic-turtlebot3`
  
  ## Set TurtleBot3 Model Name
  - `$ echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc`
  - `$ echo "export TURTLEBOT3_MODEL=waffle_pi" >> ~/.bashrc`
  
  ## Launch Simulation World
  - `$ export TURTLEBOT3_MODEL=burger`
  - `$ roslaunch turtlebot3_gazebo turtlebot3_world.launch`

 ## Run SLAM Node
  - `$ export TURTLEBOT3_MODEL=burger`
  - `$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping`
  
  
  
  ![wfawfaef](https://user-images.githubusercontent.com/60845044/125177927-8ed63f80-e1e8-11eb-9009-c427be41c066.png)
## Run Teleoperation Node to control
  - `$ export TURTLEBOT3_MODEL=burger`
  - `$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

 Control Your TurtleBot3!
 ---------------------------
 Moving around:
        w
   a    s    d
        x

 w/x : increase/decrease linear velocity
 a/d : increase/decrease angular velocity
 space key, s : force stop

 CTRL-C to quit`
 
 ![wfafesfsef](https://user-images.githubusercontent.com/60845044/125178085-0d7fac80-e1ea-11eb-8fe0-8578cfc1bd83.png)


## to save a map
- `$ rosrun map_server map_saver -f ~/map
`
