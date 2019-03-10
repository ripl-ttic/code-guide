# RIPL - Code guidelines and standards

Code guidelines and standards for projects and repositories at RIPL


## Topics for GitHub repositories

It is important to label all the repositories so that we can keep track of the functionalities that each repository provides.
On GitHub, a label is called **topic** and multiple topics can be assigned to a given repository (read the [official documentation](https://help.github.com/articles/classifying-your-repository-with-topics/) to learn how to assign topics to a repository).

It is very important to respect a labelling standard.
We support three different groups of topics, namely **Category**, **Interface**, and **Language**.
Each repository **MUST** contain at least one label for each
group. A list of allowed topics for each group follows:

### Category
<valid-topics-category>
project,
drivers,
library,
structure,
visualization,
plugin
</valid-topics-category>

### Interface
<valid-topics-interface>
native,
ros,
ros2,
lcm
</valid-topics-interface>

### Language
<valid-topics-language>
c,
c++,
python,
lua,
rust,
java,
php,
html,
matlab
</valid-topics-language>


### Topics description

A description for each topic follows.

- **Category**:
    - **project**: Repositories that are the root to a specific project. Such repositories are usually an aggregation of git submodules and are used to facilitate the deployment of an independent project.
    - **drivers**: Repositories that are responsible for talking to a physical device and presenting the retrieved data in a format that is usable by other processes. Such repositories usually involve very little data processing.
    - **library**: Repositories that provide functionalities that are useful to a high number of modules. Examples of libraries are **OpenCV** and **PCL**. They are widely used but do not provide any project-specific functionality.
    - **structure**: Repositories that are similar to **libraries** but they usually define structures and data types that other modules rely on. Examples of structural repositories are **LCM types** and **ROS messages**.
    - **visualization**: Repositories that only provide visualization capabilities. Examples are the **libbot2 viewer** and the **LCM Spy** applications.
    - **plugin**: Repositories that provide functionalities that are only accessible via another module. Such repositories usually extend the capabilities of a pre-existing component (e.g., a viewer). Examples are all the renderers used by the **liboot2 viewer** to show data published by drivers or from a software stack.

- **Interface**:
    - **native**: Indicates that the software component contained in the repository can be integrated in a larger software stack by importing its functions and classes natively.
    - **ros**: Indicates that the software component contained in the repository supports inter-process communication via the [ROS](http://www.ros.org) protocol.
    - **ros2**: Indicates that the software component contained in the repository supports inter-process communication via the [ROS2](http://www.ros2.org) protocol.
    - **lcm**: Indicates that the software component contained in the repository supports inter-process communication via the [LCM](https://lcm-proj.github.io) protocol.


## Docker images

There are 4 Docker images that you can use as a base for your module or project.
The following figure shows the hierarchy of Docker images already available on Docker Hub.

![Docker images hierarchy](https://g.gravizo.com/source/ripl_docker_hierarchy?https%3A%2F%2Fraw.githubusercontent.com%2Fripl-ttic%2Fcode-guide%2Fmaster%2FREADME.md)
<details>
<summary></summary>
ripl_docker_hierarchy
digraph prof {
 ratio = fill;
 node [style=rounded];

 ubuntu -> lcm;
 lcm -> lcm_ros;
 lcm -> libbot2;
 libbot2 -> libbot2_ros;
 libbot2 -> libbot2_pcl;
 libbot2_ros -> libbot2_pcl_ros;
 libbot2_pcl_ros -> director;

 ubuntu [label="ubuntu:16.04"];
 lcm[ \
  label="ripl/lcm:1.4.0 \n\n \
  GitHub: ripl-ttic/lcm-docker \n \
  DockerHub: ripl/lcm" \
 ];
 lcm_ros[ \
  label="ripl/lcm-ros:latest \n\n \
  GitHub: ripl-ttic/lcm-ros-docker \n \
  DockerHub: ripl/lcm-ros" \
 ];
 libbot2[ \
  label="ripl/libbot2:latest \n\n \
  GitHub: ripl-ttic/libbot2-docker \n \
  DockerHub: ripl/libbot2" \
 ];
 libbot2_ros[ \
  label="ripl/libbot2-ros:latest \n\n \
  GitHub: ripl-ttic/libbot2-ros-docker \n \
  DockerHub: ripl/libbot2-ros" \
 ];
 libbot2_pcl[ \
  label="ripl/libbot2-pcl:latest \n\n \
  GitHub: ripl-ttic/libbot2-pcl-docker \n \
  DockerHub: ripl/libbot2-pcl" \
 ];
 libbot2_pcl_ros[ \
  label="ripl/libbot2-pcl-ros:latest \n\n \
  GitHub: ripl-ttic/libbot2-pcl-ros-docker \n \
  DockerHub: ripl/libbot2-pcl-ros" \
 ];
 director[ \
  label="ripl/director:latest \n\n \
  GitHub: afdaniele/director \n \
  DockerHub: ripl/director" \
 ];
}
ripl_docker_hierarchy
</details>
