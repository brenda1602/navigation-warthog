# navigation-warthog
### Warthog + Velodyne 
 The [Warthog](https://github.com/warthog-cpr/warthog) robot was equipped with [Velodyne](https://github.com/lmark1/velodyne_simulator) 16 Lidar, so the packages warthog_description and warthog_control was modified
#### 
### Methods 
  - [Gmapping](http://wiki.ros.org/gmapping)
  - [AMCL](http://wiki.ros.org/amcl)
  - [Hector SLAM](http://wiki.ros.org/hector_slam)
### instructions

  ```
  # Clone the repositories
    $ git clone https://github.com/lmark1/velodyne_simulator
    $ git clone https://github.com/warthog-cpr/warthog
    $ git clone https://github.com/lmark1/velodyne_simulator
    $ git clone https://github.com/brenda1602/navigation-warthog/
  ```
  ```
  # Include the files for configure the velodyne 
    $ cp navigation-warthog/warthog_description/urdf/accessories/VLP-16.urdf.xacro warthog/warthog_description/urdf/accessories
  ```
  Replace the files warthog/warthog_description/VLP-16.urdf.xacro and warthog_control/config/control.yaml and include keyboard_teleop.launch
  
  ```
    $ rm warthog/warthog_description/urdf/accessories/VLP-16.urdf.xacro warthog_control/config/control.yaml
    $ cp navigation-warthog/warthog_description/VLP-16.urdf.xacro   warthog/warthog_description/urdf/accessories
    $ cp navigation-warthog/warthog_control/control.yaml   warthog/warthog_control/config
    $ cp navigation-warthog/warthog_control/keyboard_teleop.launch   warthog/warthog_control/launch
  ```
  Run the simulation
  ```
    $ catkin _male
    $ source devel/setup.bash
    $ roslaunch warthog_navigation gmappinh_demo.launch
  ```
  
