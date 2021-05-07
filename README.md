# ssm_safety

The module provides an optimized speed and separation monitoring package to slow down the robot in case of human-robot proximity.
The module needs the information on the target trajectory, and the actual robot position. Then, the position is projected on the trajectory, and using the information on the human position with respect to the robot, the scaling override is computed. 

The module subscribes:  

- a message of the type sensor_msgs::JointState with the unscaled joint target. 

- a message of the type geometry_msgs::PoseArray containing the poses of human body parts (i.e. a human) in the scene reference frame. 

- an user-defined speed override of the type std_msgs::Int64  

The module publishes: 

- a message of the type std_msgs::Int64 containing the safety override 0-100 (the topics are two, with the same content, to have a redundant communication channel) 
