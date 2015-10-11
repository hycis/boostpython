cmake_minimum_required(VERSION 3.3)

find_package(PythonLibs REQUIRED)
include_directories(${PYTHON_INCLUDE_DIRS})
find_package(Boost REQUIRED)
include_directories(${BOOST_INCLUDE_DIRS})
SET(Boost_USE_STATIC_LIBS OFF)

# cannot build SHARED object
add_library(hello_ext SHARED hello_ext.cpp)

find_package(Boost COMPONENTS python REQUIRED)
target_link_libraries(hello_ext
  ${Boost_PYTHON_LIBRARY}
)
