# acados_catkin

This repo wraps an acados installation in a catkin package to simplify usage in catkin based projects

## Usage

Add `<depend>acados_catkin</depend>` to the `package.xml`. Simply add `catkin_INCLUDE_DIRS` to your `include_directories` and by link your target using acados aginst `catkin_LIBRARIES`.
