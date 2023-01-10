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
        libdbcppp
        GIT_REPOSITORY https://github.com/xR3b0rn/dbcppp
        GIT_TAG fa8ce17468737abe855d61128fee86f3330bd516 # latest commit as of Jan 10, 2023
)


FetchContent_MakeAvailable(libdbcppp)
FetchContent_MakeAvailable(argparse)


add_executable(dbcppp_cmake main.cpp)
target_link_libraries(dbcppp_cmake PRIVATE libdbcppp argparse)
