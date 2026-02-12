# ROS2 Docker Setup and C++ Pub/Sub

## Workspace Structure (3.8.2)

Screenshot of the `tree -L 4 ros2_ws` output is included.

## Message Flow Diagram (3.8.3)

```mermaid
flowchart LR
  Talker["/talker (C++)"] -->|publishes std_msgs/String| Chatter["/chatter topic"]
  Chatter -->|delivers messages| Listener["/listener (C++)"]


Build Instructions

source /opt/ros/humble/setup.bash
cd /workspace/ros2_ws
colcon build
source install/setup.bash

Terminal 1

ros2 run demo_cpp_pubsub listener

Terminal 2

ros2 run demo_cpp_pubsub talker


