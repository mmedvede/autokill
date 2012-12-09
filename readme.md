
Autokill: quicker ROS debugging.
================================

Autokill is a tool that allows faster ROS iterative debugging:
write code, save/compile, and see the result immediately.

The idea is to detect when the binary for a node has been changed. Then restart the node.

Usage
=====

For example, if you are working on a node `my_node` in the package `cool_stuff_ros` use the following snippet inside your launch file to run the node (respawn is mandatory):


```
<node name="my_node" pkg="cool_stuff_ros" type="my_node" respawn="true"/>
<node name="my_node_killer" pkg="autokill" type="autokill" args="$(find cool_stuff_ros)/path/to/my_node my_node"/>
```

