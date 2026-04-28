cmake_minimum_required(VERSION 3.10)
project(ChatRoom-CPP)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Find Boost
find_package(Boost REQUIRED COMPONENTS system thread)

# Include directories - make sure the path is correct
include_directories(${CMAKE_SOURCE_DIR}/include)
include_directories(${Boost_INCLUDE_DIRS})

# Add header files explicitly
set(HEADER_FILES
    include/chatroom.hpp
    include/message.hpp
)

# Server executable
add_executable(server 
    src/chatroom.cpp
    ${HEADER_FILES}
)

# Client executable
add_executable(client
    src/client.cpp
    ${HEADER_FILES}
)

# Link libraries
target_link_libraries(server PRIVATE
    ${Boost_LIBRARIES}
    pthread
)

target_link_libraries(client PRIVATE
    ${Boost_LIBRARIES}
    pthread
)

# Set output directories
set_target_properties(server client
    PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)