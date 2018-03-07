CMAKE_MINIMUM_REQUIRED(VERSION 2.4)
PROJECT(KalmanFilter)
include_directories("${PROJECT_SOURCE_DIR}")
add_library(KalmanFilter SHARED Kalman.cpp)
set_target_properties(KalmanFilter PROPERTIES VERSION "1.0.0" SOVERSION "1")
set(KalmanFilter_LIBRARIES KalmanFilter)
install(TARGETS KalmanFilter
    EXPORT KalmanFilter-export
    LIBRARY        DESTINATION lib
    INCLUDES       DESTINATION include
    PUBLIC_HEADER  DESTINATION include/KalmanFilter)
install(FILES Kalman.h DESTINATION include/KalmanFilter)
install(EXPORT KalmanFilter-export
    FILE KalmanFilterConfig.cmake
    DESTINATION share/cmake/KalmanFilter/)
