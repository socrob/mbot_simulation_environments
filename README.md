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

![alt ERL_gazebo_testbed](https://github.com/socrob/mbot_simulation_environments/blob/kinetic/doc/erl_testbed.png "ERL testbed")

Installations instructions
==========================

Clone and compile the code into your catkin workspace:

        git clone https://github.com/socrob/mbot_simulation_environments.git
        catkin build
        source ~/.bashrc

Launch:

        roslaunch mbot_simulation_environments load_environment_example.launch

Enjoy!

If errors, please report bugs by using the issues in this repository
