# MoveIt! MoveGroup tutorial for UR5 (python interface)

Adaptation of [MoveIt! MoveGroup tutorial for Panda](https://github.com/ros-planning/moveit_tutorials/blob/kinetic-devel/doc/move_group_python_interface/)

## Installation

We need to use fixed URDF/SRDF universal_robotics package (see [here](https://github.com/ros-industrial/universal_robot/pull/284)).
Thus, we use a custom `universal_robot` repository.

``` 
mkdir -p ur5_ws/src && cd ur5_ws/src
git clone https://github.com/vfdev-5/universal_robot
git clone https://github.com/vfdev-5/move_group_tutorial_ur5.git
cd ../ & catkin_make
```

we need also to fix problem with `pyassimp`:
```
pip install --upgrade pyassimp
```

Install other dependencies:
```
cd ur5_ws/ && rosdep install --from-paths src --ignore-src -r -y
```

## Usage:

Terminal 1
```
cd ur5_ws && source devel/setup.bash
roslaunch ur5_moveit_config demo.launch limited:=true
```

Terminal 2
```
cd ur5_ws && source devel/setup.bash
python src/move_group_tutorial_ur5/src/move_group_tutorial_ur5.py
```
