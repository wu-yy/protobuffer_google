cmake_minimum_required(VERSION 3.12)
project(protobuf)

SET(CMAKE_CXX_FLAGS "-g -Wall -Werror -std=c++11")
#CXXFLAGS="$(pkg-config --cflags protobuf)"
#
#LIBS="$(pkg-config --libs protobuf)"

set(CMAKE_CXX_STANDARD 11)

INCLUDE(FindProtobuf)
FIND_PACKAGE(Protobuf REQUIRED)
INCLUDE_DIRECTORIES(${PROTOBUF_INCLUDE_DIR})
PROTOBUF_GENERATE_CPP(PROTO_SRC PROTO_HEADER addressbook.proto)
ADD_LIBRARY(proto2 ${PROTO_HEADER} ${PROTO_SRC})
TARGET_LINK_LIBRARIES(proto2)


INCLUDE_DIRECTORIES(${CMAKE_CURRENT_BINARY_DIR})

add_executable(protobuf main.cpp)
TARGET_LINK_LIBRARIES(protobuf proto2 ${PROTOBUF_LIBRARY})