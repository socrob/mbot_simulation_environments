mbot_simulation_environments
============================

Gazebo European Robotics League (ERL) arena simulation environment.

Brought to you by:

- Instituto Superior Tecnico, Lisboa
- Institute for Systems and Robotics (ISR)
- Laboratório de Robótica e Sistemas em Engenharia e Ciência (LARSyS)
- SocRob RoboCup team

To see a video of how the models were textured, you can see this youtube tutorial
video [part1](https://www.youtube.com/watch?v=Xo2vIfcjfJw&lc=z23ls5sxhsvmzzlvyacdp435jacfcr5kh2ncmq1423xw03c010c)
[part2](https://www.youtube.com/watch?v=5Jr1flkjQoU&t=19s)

This code was tested on Ubuntu 16.04 and ROS kinetic with Gazebo 7

This is how the simulation looks like:

![alt ERL_gazebo_testbed](https://github.com/socrob/mbot_simulation_environments/blob/kinetic/doc/erl_testbed.jpg "ERL testbed")

Installations instructions
==========================

Clone and compile the code into your catkin workspace:

        git clone https://github.com/socrob/mbot_simulation_environments.git
        catkin build
        source ~/.bashrc

Launch:

        roslaunch mbot_simulation_environments load_environment_example.launch

Sample Launch file to spawn your own robot in this:

```
<?xml version="1.0"?>
<launch>

    <!-- whether you want gazebo gui or not (saves resources if you set this to false) -->
    <arg name="gazebo_gui" default="false" />

    <!-- select your world -->
    <arg name="world_name" default="isr-testbed.world" /> <!-- set to "empty.world" for empty world -->
    <arg name="world_path" default="$(find mbot_simulation_environments)/worlds" /> <!-- set to "worlds" empty world -->

    <!-- launch robot environment -->
    <include file="$(find mbot_simulation_environments)/launch/load_environment_example.launch" >
        <arg name="world_name" value="$(arg world_name)" />
        <arg name="world_path" value="$(arg world_path)" />
        <arg name="gazebo_gui" value="$(arg gazebo_gui)" />
    </include>
    
    <!-- upload URDF model of the robot to parameter server -->
    <param name="robot_description"
           command="$(find xacro)/xacro --inorder $(find your_robot_description)/xacro/my_robot_urdf.urdf.xacro" />
    
    <!-- spawn mbot (in a certain position and with a default arm configuration) -->
    <node pkg="gazebo_ros" type="spawn_model" name="mbot_spawner"
          args="-package_to_model -urdf -model mbot -param robot_description -x 0.5 -y 0.5 -z 0.01
          -J left_arm_joint0 0.0
          -J left_arm_joint1 1.18
          -J left_arm_joint2 0.12
          -J left_arm_joint3 0.92
          -J left_arm_joint4 0.24
          -J left_arm_joint5 0.63
          -J left_arm_joint6 0.44" />
          
</launch>
```

Enjoy!

If errors, please report bugs by using the issues in this repository
