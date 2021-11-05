PROJECT(llvm-spirv-backend)
cmake_minimum_required(VERSION 2.8)
get_filename_component(FIPS_ROOT_DIR "../fips" ABSOLUTE)
include("${FIPS_ROOT_DIR}/cmake/fips.cmake")

if(NOT FIPS_IMPORT)
	fips_project(llvm-spirv)
	fips_setup()
endif()

	SET(LLVM_ROOT ${CMAKE_CURRENT_SOURCE_DIR})
	get_filename_component(ANYFX_SOURCE_DIR "llvm-spirv-backend" ABSOLUTE)

	fips_add_subdirectory(llvm)

if(NOT FIPS_IMPORT)
    fips_finish()
endif()
