PROJECT(llvm-spirv)
cmake_minimum_required(VERSION 3.22)
get_filename_component(FIPS_ROOT_DIR "../fips" ABSOLUTE)
include("${FIPS_ROOT_DIR}/cmake/fips.cmake")

if(NOT FIPS_IMPORT)
	fips_project(llvm-spirv)
	fips_setup()
endif()


	SET(LLVM_ROOT ${CMAKE_CURRENT_SOURCE_DIR})
	#SET(${LLVM_CMAKE_DIR} ${CMAKE_CURRENT_BINARY_DIR}/llvm/cmake/modules)
	#INCLUDE_DIRECTORIES(${CMAKE_CURRENT_BINARY_DIR}/llvm/include)
	#SET(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH};${LLVM_ROOT}/llvm/cmake/modules;${LLVM_ROOT}/mlir/cmake/modules)
	SET(LLVM_BUILD_EXAMPLES OFF)
	SET(LLVM_BUILD_TESTS OFF)
	SET(LLVM_INCLUDE_EXAMPLES OFF)
	SET(LLVM_INCLUDE_BENCHMARKS OFF)
	SET(LLVM_BUILD_BENCHMARKS OFF)
	SET(LLVM_ENABLE_PROJECTS mlir)

	get_filename_component(ANYFX_SOURCE_DIR "llvm-spirv" ABSOLUTE)

	SET(CMAKE_FOLDER "LLVM")
	fips_add_subdirectory(llvm)
	SET(CMAKE_FOLDER "")
	#fips_add_subdirectory(mlir)

if(NOT FIPS_IMPORT)
    fips_finish()
endif()
