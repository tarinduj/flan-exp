cmake_minimum_required(VERSION 3.10)

project(my_project)

# Abseil requires C++14
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_BUILD_TYPE Release)
set(CMAKE_CXX_FLAGS_RELEASE "-O3")

# Process Abseil's CMake build system
add_subdirectory(abseil-cpp)

add_executable(abseil_pa_manual.out abseil_pa_manual.cpp)

# Declare dependency on the absl::* libraries
target_link_libraries(abseil_pa_manual.out absl::flat_hash_map absl::flat_hash_set)

# mkdir build
# cd build 
# cmake ..
# cmake --build . --target abseil_pa_manual.out