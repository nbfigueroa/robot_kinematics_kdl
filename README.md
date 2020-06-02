## robot_kinematics_kdl

This library includes KDL operations to compute the forwards kinematics and Jacobian of a robotic arm using the URDF representation of the robot (no DH parameters necessary). 

It also contains a stripped-down version of the [cob_twist_controller](http://wiki.ros.org/cob_twist_controller) which is a package that contains several implemented inverse kinematics approaches at the velocity level. Namely, given a desired cartesian velocity or twits it maps them to joint velocities we use the low-level velocitis with either of the following approaches:

 - WLN:  "Weighted-least-norm base, with identity as weighting matrix (equal to None)"
 - GPM:  "Gradient-projection-method"
 - STACK_OF_TASKS:  "Task Priority Strategy for all with dynamic resadjust of GPM and task ..."
 - TASK_2ND_PRIO: "Task Priority Strategy for obstacle avoidance ..."
 - UNIFIED_JLA_SA: "Inv Kinematics solver based on unified weighted least norm and sigmoid weighting functions"

Selecting the IK approach and tuning parameters can be done via [dynamic reconfigure GUI](http://wiki.ros.org/rqt_reconfigure) defined in ``/cfg/TwistController.cfg`` or changing the parameters in the configuration yaml file ``config/  
    
---
## System Requirements
* This code was written for ROS Indigo in Ubuntu 14.04.
* Still needs to be tested on ROS Kinetic in Ubuntu 16.04 and ROS Melodic on Ubuntu 18.08

## Installation, Dependencies and Compilation
Do the following steps:
* In your catkin src directory clone the repository
```
$ git clone https://github.com/nbfigueroa/robot_kinematics_kdl.git
```
* wstool gets all other git repository dependencies, after the following steps you should see extra catkin 
  packages in your src directory.
```
$  wstool init
$  wstool merge robot_kinematics_kdl/dependencies.rosinstall 
$  wstool up 
```
* Query and installs all libraries and packages 
```
$ rosdep install --from-paths . --ignore-src --rosdistro indigo 
```
* Finally complie
```bash
  $ cd ~/catkin_ws
  $ catkin_make
  $ source devel/setup.bash
  $ catkin_make
```
  You might need to source the `./bashrc` file and compile again if the first compliation could not find some of the in-house dependencies. If `roscd` doesn't find the compiled packages run `rospack profile`.

---
## Usage



### Forward Kinematics
............
............

### Inverse (and Forward) Kinematics
```bash
$ roslaunch cob_twist_controller test_cobot_IKsolver.launch
```


---
## Contact
Maintainer: [Nadia Figueroa ](https://nbfigueroa.github.io/)(nadiafig @ mit dot edu)

## License
- The original version of the IK implementations taken from [cob_twist_controller](http://wiki.ros.org/cob_twist_controller) were licensed under Apache 2.0. 
- This code is released under MIT license.

