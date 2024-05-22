cmake_minimum_required(VERSION 3.10.0)

project(InstantMeshes
  VERSION 1.0.0
  DESCRIPTION "Instant Meshes Library"
  )

list(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/CMake")
find_package(Eigen3 3.4 REQUIRED)
find_package(TBB REQUIRED)

if (NOT DEFINED BIN_DIR)
  set (BIN_DIR bin)
endif (NOT DEFINED BIN_DIR)

if (NOT DEFINED LIB_DIR)
  set (LIB_DIR lib)
endif (NOT DEFINED LIB_DIR)

if (NOT DEFINED INCLUDE_DIR)
  set (INCLUDE_DIR include)
endif (NOT DEFINED INCLUDE_DIR)

add_subdirectory(include)
add_subdirectory(src)

# Local Variables:
# tab-width: 8
# mode: cmake
# indent-tabs-mode: t
# End:
# ex: shiftwidth=2 tabstop=8
