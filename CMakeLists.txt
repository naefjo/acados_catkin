cmake_minimum_required(VERSION 3.10.2)
project(acados_catkin)

find_package(catkin REQUIRED)
find_package(acados REQUIRED)

if(acados_FOUND)
    get_target_property(acados_INCLUDE_DIRS acados INTERFACE_INCLUDE_DIRECTORIES)
    set(blasfeo_INCLUDE_DIRS "${acados_INCLUDE_DIRS}/blasfeo/include")
    set(hpipm_INCLUDE_DIRS "${acados_INCLUDE_DIRS}/hpipm/include")
    
else()
    message(FATAL_ERROR "Did not find acados using find_package. Make sure it is installed on your system.")
endif()

catkin_package(
    INCLUDE_DIRS ${acados_INCLUDE_DIRS} ${blasfeo_INCLUDE_DIRS} ${hpipm_INCLUDE_DIRS}
    LIBRARIES acados
)