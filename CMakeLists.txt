cmake_minimum_required(VERSION 2.8.3)
project(ar_pose_msgs)

#List to make rest of code more readable
set( MESSAGE_DEPENDENCIES
    geometry_msgs
)

#Declare build dependencies
find_package(catkin REQUIRED 
    COMPONENTS
    message_generation
    ${MESSAGE_DEPENDENCIES} )

#Add message files
add_message_files(DIRECTORY msg
    FILES
    ARMarker.msg
    ARMarkers.msg
)

#And now generate the messages
generate_messages(DEPENDENCIES ${MESSAGE_DEPENDENCIES})

#Declare package run-time dependencies
catkin_package( CATKIN_DEPENDS message_runtime ${MESSAGE_DEPENDENCIES})