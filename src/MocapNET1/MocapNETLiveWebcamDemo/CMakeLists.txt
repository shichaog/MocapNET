project( MocapNETLiveWebcamDemo ) 
cmake_minimum_required( VERSION 2.8.7 )   
#cmake_minimum_required(VERSION 3.5)
find_package(OpenCV REQUIRED)
INCLUDE_DIRECTORIES(${OpenCV_INCLUDE_DIRS})

include_directories(${TENSORFLOW_INCLUDE_ROOT})


add_executable(MocapNETLiveWebcamDemo ${BVH_SOURCE} ${OPENGL_SOURCE} mocapNETLiveDemo.cpp cameraControl.cpp ../MocapNETLib/opengl.cpp ../MocapNETLib/bvh.cpp ../MocapNETLib/csv.cpp ../MocapNETLib/visualization.cpp ../MocapNETLib/remoteExecution.cpp ../MocapNETLib/tools.cpp ../MocapNETLib/jsonCocoSkeleton.cpp ../../../dependencies/InputParser/InputParser_C.cpp ../MocapNETLib/gestureRecognition.cpp ../MocapNETLib/outputFiltering.cpp utilities.cpp ../../Tensorflow/tensorflow.cpp ../../Tensorflow/tf_utils.cpp  )

target_link_libraries(MocapNETLiveWebcamDemo rt dl m pthread ${OpenCV_LIBRARIES} ${OPENGL_LIBS} Tensorflow  TensorflowFramework MocapNETLib ${NETWORK_CLIENT_LIBRARIES} ${PNG_Libs} ${JPG_Libs} )
set_target_properties(MocapNETLiveWebcamDemo PROPERTIES DEBUG_POSTFIX "D") 


set_target_properties(MocapNETLiveWebcamDemo PROPERTIES 
                       ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_SOURCE_DIR}"
                       LIBRARY_OUTPUT_DIRECTORY "${CMAKE_SOURCE_DIR}"
                       RUNTIME_OUTPUT_DIRECTORY "${CMAKE_SOURCE_DIR}"
                      )

