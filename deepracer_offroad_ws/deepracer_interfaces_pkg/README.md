# AWS DeepRacer interfaces package for AWS DeepRacer Offroad

## Overview

The AWS DeepRacer interfaces ROS package is a foundational package that creates the custom service and message types that are used in the core AWS DeepRacer application. Here we have extended and modified the package to support DeepRacer Offroad sample project. These services and messages defined are shared across the packages that are part of the AWS DeepRacer application and DeepRacer Offroad sample project. For more information about the DeepRacer Offroad project, see [DeepRacer Offroad sample project](https://github.com/ThatGuyIKnow/aws-deepracer-maze-solver).

## License

The source code is released under [Apache 2.0](https://aws.amazon.com/apache-2-0/).

## Installation

Follow these instructions to install the AWS DeepRacer interfaces package.

### Prerequisites

The AWS DeepRacer device comes with all the prerequisite packages and libraries installed to run the DeepRacer Offroad sample project. For more information about the pre-installed set of packages and libraries on the AWS DeepRacer and about installing the required build systems, see [Getting started with AWS DeepRacer OpenSource](https://github.com/aws-deepracer/aws-deepracer-launcher/blob/main/getting-started.md).

The `deepracer_inferfaces_pkg` specifically depends on the following ROS 2 packages as build and execute dependencies:

1. `rosidl_default_generators`: The custom-built interfaces rely on `rosidl_default_generators` for generating language-specific code.
2. `rosidl_default_runtime`: The custom-built interfaces rely on `rosidl_default_runtime` for using the language-specific code.
3. `sensor_msgs`: This package defines messages for commonly used sensors, including cameras and scanning laser rangefinders.
4. `std_msgs`: This package sends standard ROS messages, including common message types representing primitive data types, and other basic message constructs, such as multiarrays.



## Downloading and building

Open a terminal on the AWS DeepRacer device and run the following commands as the root user.

1. Switch to the root user before you source the ROS 2 installation:

        sudo su

1. Source the ROS 2 Foxy setup script:

        source /opt/ros/foxy/setup.bash

1. Create a workspace directory for the package:

        mkdir -p ~/deepracer_ws
        cd ~/deepracer_ws

1. Clone the entire AWS DeepRacer Offroad sample project on the AWS DeepRacer device:

        git clone https://github.com/ThatGuyIKnow/aws-deepracer-maze-solver.git
        cd ~/deepracer_ws/aws-deepracer-maze-solver/deepracer_offroad_ws/

1. Resolve the dependencies:

        cd ~/deepracer_ws/aws-deepracer-maze-solver/deepracer_offroad_ws/ && rosdep install -i --from-path . --rosdistro foxy -y

1. Build the `deepracer_interfaces_pkg`:

        cd ~/deepracer_ws/aws-deepracer-maze-solver/deepracer_offroad_ws/ && colcon build --packages-select deepracer_interfaces_pkg

## Resources

* [Getting started with AWS DeepRacer OpenSource](https://github.com/aws-deepracer/aws-deepracer-launcher/blob/main/getting-started.md)
* [Getting started with the AWS DeepRacer Offroad sample project](https://github.com/ThatGuyIKnow/aws-deepracer-maze-solver/blob/main/getting-started.md)
