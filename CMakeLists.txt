cmake_minimum_required(VERSION 3.12)
project(cpp_eval)
 
set(CMAKE_CXX_STANDARD 11)
find_package(DLIB REQUIRED)

if (POLICY CMP0115)
    # suppress warnings about missing filename extensions caused by policy
    # CMP0115, introduced with CMake 3.20
    cmake_policy(SET CMP0115 OLD)
endif()

include_directories(${DLIB_INCLUDE_DIR})
add_executable(cpp_eval dlib_3d)
target_link_libraries(cpp_eval ${DLIB_LIBRARIES} dlib::dlib)
