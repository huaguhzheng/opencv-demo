cmake_minimum_required(VERSION 3.10)
project(openCVDemo)
find_package(OpenCV REQUIRED)
include_directories( ${OpenCV_INCLUDE_DIRS} )
set(CMAKE_CXX_STANDARD 11)

add_executable(showimage showImage.cpp)
target_link_libraries(showimage ${OpenCV_LIBS})

add_executable(cvMat cvMat.cpp)
target_link_libraries(cvMat ${OpenCV_LIBS})

add_executable(colorReduce colorReduce.cpp util/colorReduce.cpp util/colorReduce.h)
target_link_libraries(colorReduce ${OpenCV_LIBS})

add_executable(laplace laplace.cpp util/sharpen.cpp util/sharpen.h)
target_link_libraries(laplace ${OpenCV_LIBS})

add_executable(operator operator.cpp)
target_link_libraries(operator ${OpenCV_LIBS})

add_executable(remap image-remap/remap.cpp)
target_link_libraries(remap ${OpenCV_LIBS})

add_executable(color-detector color-detect/main.cpp color-detect/Detector.h color-detect/Detector.cpp)
target_link_libraries(color-detector ${OpenCV_LIBS})

add_executable(grab-cut grab-cut/grab-cut.cpp)
target_link_libraries(grab-cut ${OpenCV_LIBS})
