# RIPL - Code guidelines and standards

Code guidelines and standards for projects and repositories at RIPL


## Topics for GitHub repositories

It is important to label all the repositories so that we can keep track of what functionalities each repo provides.
It is also important to respect a labelling standard. On GitHub, a label is a **topic** that gets assigned to a repository (read the [official documentation](https://help.github.com/articles/classifying-your-repository-with-topics/) to learn how to assign topics to a repository).

We support three different groups of labels, namely **Category**, **Interface**, and **Language**.
Each repository must contain at least one label for each
group. A list of allowed topics for each group follows:

- **Category**:
<valid-topics-category>
project,
drivers,
library,
structure,
visualization,
plugin
</valid-topics-category>

- **Interface**:
<valid-topics-interface>
native,
ros,
ros2,
lcm
</valid-topics-interface>

- **Language**:
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

A description for each label follows.

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
