cmake_minimum_required(VERSION 2.8)

set(SOURCES main.cpp)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -ggdb3 -std=c++11")

list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_LIST_DIR}/CMake")
find_package(MLPACK REQUIRED)
find_package(Armadillo REQUIRED)

include_directories(${MLPACK_INCLUDE_DIRS} ${ARMADILLO_INCLUDE_DIRS})

add_executable(mnist ${SOURCES})
target_link_libraries(mnist ${MLPACK_LIBRARIES} ${ARMADILLO_LIBRARIES})
