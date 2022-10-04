### Instructions to use the package launch files

Create the catkin_ws and src directories, and move the package launch files into `src`:
```
touch catkin_ws/src
cd catkin_ws
```

Build the package:
```
catkin_make
```

Navigate to the `src` directory and run the following:
```
source /devel/setup.bash
roslaunch lab_3_Bags bags.launch
```

### Optional Parameters:

* `use_xacro:=` toggles the use of the xacro file. The xacro file used here is the `navvis.xacro` file from the previous part. This is set to false by default, and will accept `true` and `false`. 
* `publisher_gui:=` toggles the use of the joint-state-publisher-gui. This is set to true by default, and will accept `true` and `false`
* `use_robot_state_publisher:=` toggles the use of robot state publisher. This is set to true by default, and will accept `true` and `false`
* `use_this_xacro:=` toggles the use of this the `bags.xacro` file associated with this part of the lab. This is set to false by default, and will accept `true` and `false`

Example uses of the `roslaunch` command with optional parameters:
```
roslaunch lab_3_Bags bags.launch use_this_xacro:=true
roslaunch lab_3_Bags bags.launch use_xacro:=true use_robot_state_publisher:=false
```


### Launching with rosbag and map_server
This launch file is slightly modified to take take an optional parameter `bag_file` and run that file along with the map server. This launch file will search for the `maps_glennan` package and use the `glennan5_map.yaml` file.

Run this file by using:
```
roslaunch lab_3_Bags bags_with_bag_file.launch bagfile:=<location_of_bag_file>
```
By default, this launch file will use the `glennan_5_basic.bag` if it is located within the package. You can change this by replacing `<location_of_bag_file>` with the file path of the bag file you wish to use.
