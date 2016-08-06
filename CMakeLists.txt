cmake_minimum_required(VERSION 2.8)

project(Slic_Superpixel	)

find_package(OpenCV REQUIRED)

include_directories(
      include
)

add_library(slic_superpixel src/slic.cpp)
add_executable(slic_test src/test_slic.cpp)

target_link_libraries( slic_superpixel 
       ${OpenCV_LIBS}
)

target_link_libraries( slic_test
       slic_superpixel
)
