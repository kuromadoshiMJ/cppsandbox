# cmake version to be used
cmake_minimum_required( VERSION 3.0 )

# project name
project(helloworld)

# target
add_executable( helloworld helloworld.cc )

# external libs
find_package(Ceres REQUIRED)
# Or find_package(Ceres REQUIRED PATHS "/path/to/install/dir") if the install directory is not in your PATH

target_include_directories(helloworld
  PRIVATE
    ${CERES_INCLUDE_DIRS}
)

target_link_libraries(helloworld
  PRIVATE
    ${CERES_LIBRARIES}
)