# gazebo_models

urdf机器人模型功能包。

## 运行方法

```sh
$ roslaunch gazebo_models display_gazebo_rviz.launch     #在gazebo和rviz中同时显示机器人
``` 

## TODO
- [ ] Add func to track the ball by the camera
- [ ] Add kick server to move the ball
- [ ] Add turtlebot3 to the field

## Launch files in turtlebot3
```bash
$ export TURTLEBOT3_MODEL=${TB3_MODEL}
$ roslaunch turtlebot3_gazebo turtlebot3_empty_world.launch
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
$ roslaunch turtlebot3_gazebo turtlebot3_gazebo_rviz.launch
```
* `turtlebot3_empty_world.launch` just launches a world containing the turtlebot3
    * tf relations here only contains the tf from odom to basefoot_print
    * change the **publishWheelTf** in `turtlebot3_burger.gazebo.xacro` to pulish the tf from base_link to wheel links
* `turtlebot3_teleop_key.launch` just publishes cmd_vel(a Twist value).
* `turtlebot3_gazebo_rviz.launch` luanches `turtlebot3_remote.launch`
    * `turtlebot3_remote.launch` runs a **robot_state_publisher**, then publishes the joint states to Rviz



