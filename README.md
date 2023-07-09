Mobile robot navigation with ROS.

## Start empty simulator:

ros2 launch mobile-robot-navigation launch_sim.launch.py

## Start simulator with obstacles:

ros2 launch mobile-robot-navigation launch_sim.launch.py world:=./src/mobile-robot-navigation/worlds/obstacles.world

## Start teleoperation with Gazebo controls:

ros2 run teleop_twist_keyboard teleop_twist_keyboard

## Start teleoperation with ROS2 controls:

ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args -r /cmd_vel:=/diff_cont/cmd_vel_unstamped

## Windows 10 WSL2 Gazebo fix rendering (enable Gazebo CPU rendering):

export GAZEBO_IP=127.0.0.1
export DISPLAY=$(cat /etc/resolv.conf | grep nameserver | awk '{print $2}'):0
export LIBGL_ALWAYS_INDIRECT=0
export LIBGL_ALWAYS_SOFTWARE=1
source /usr/share/gazebo/setup.sh
