cmake_minimum_required(VERSION 3.2)

file(GLOB_RECURSE SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/Source" *.cxx *.h *.c)

include_directories("${CMAKE_CURRENT_SOURCE_DIR}/Source/CParse"
		"${CMAKE_CURRENT_SOURCE_DIR}/Source/DOH"
		"${CMAKE_CURRENT_SOURCE_DIR}/Source/Include"
		"${CMAKE_CURRENT_SOURCE_DIR}/Source/Modules"
		"${CMAKE_CURRENT_SOURCE_DIR}/Source/Preprocessor"
		"${CMAKE_CURRENT_SOURCE_DIR}/Source/Swig")

add_executable(swig_temp ${SOURCES})

add_custom_target(swig
		make -j8
		WORKING_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}"
		SOURCES ${SOURCES})