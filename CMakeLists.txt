cmake_minimum_required(VERSION 3.24)
project(dbcppp_cmake)

set(CMAKE_CXX_STANDARD 17)


# fetch argparse 2.6
include(FetchContent)
FetchContent_Declare(
        argparse
        GIT_REPOSITORY https://github.com/p-ranav/argparse.git
        GIT_TAG 40a3888f151256bba95c45860af381b2b73752e8 # v2.6
)
# fetch dbcppp
FetchContent_Declare(
        dbcppp
        GIT_REPOSITORY https://github.com/xR3b0rn/dbcppp
        GIT_TAG 54ce78ad53442db94e03d16a4fd5f3b339dab193
)


FetchContent_MakeAvailable(dbcppp)
FetchContent_MakeAvailable(argparse)


add_executable(dbcppp_cmake main.cpp)
target_link_libraries(dbcppp_cmake PRIVATE dbcppp argparse)
