cmake_minimum_required(VERSION 2.8.3)
project(roboskel_msgs)

find_package(catkin REQUIRED COMPONENTS
    std_msgs
    sensor_msgs
    message_generation
)

find_package(message_generation)

add_message_files(
    FILES
    PointCloud2_Segments.msg
    ClusteredLaserScans.msg
    LaserScanCluster.msg
    LaserScans.msg
    Mission.msg
)

add_service_files(
    FILES
    StringAndBool.srv
)

generate_messages(
    DEPENDENCIES
    std_msgs
    sensor_msgs
)


catkin_package(
    CATKIN_DEPENDS message_runtime
)

include_directories(
    ${catkin_INCLUDE_DIRS}
)

