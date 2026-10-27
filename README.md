# navigation2_course_ackermann
## To start, download and install this repository
### Then start
At first build project:
``` bash
colcon build --packages-select car_gazebo toyota car_control
```
``` bash
source install/setup.bash
```
Run simulation
``` bash
ros2 launch car_gazebo car_gazebo.launch.py
```
Then you can check rviz2
``` bash
rviz2 --ros-args   -r /tf:=/car/tf   -r /tf_static:=/car/tf_static   -r /robot_description:=/car/robot_description
```
You may use teleopkey
``` bash
ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args   -p stamped:=true   -r cmd_vel:=/car/ackermann_steering_controller/reference
```
You may check tf tree:
``` bash
ros2 run rqt_tf_tree rqt_tf_tree --ros-args -r /tf:=/car/tf -r /tf_static:=/car/tf_static
```
