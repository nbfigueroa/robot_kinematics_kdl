## robot_kinematics_kdl

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
............
............

---
## Contact
Maintainer: [Nadia Figueroa ](https://nbfigueroa.github.io/)(nadiafig @ mit dot edu)

## License
- This code is released under MIT license.

