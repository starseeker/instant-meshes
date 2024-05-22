set(IM_SRCS
  adjacency.cpp
  bvh.cpp
  cleanup.cpp
  dedge.cpp
  extract.cpp
  field.cpp
  hierarchy.cpp
  meshstats.cpp
  normal.cpp
  reorder.cpp
  serializer.cpp
  smoothcurve.cpp
  subdivide.cpp
  )

# Add the library.
add_library(InstantMeshes SHARED ${IM_SRCS})

target_include_directories(InstantMeshes PRIVATE
  ${CMAKE_SOURCE_DIR}/include
  ${CMAKE_SOURCE_DIR}/include/ext
  ${TBB_INCLUDE_DIRS}
  ${EIGEN_INCLUDE_DIRS}
  )

target_link_libraries(InstantMeshes PRIVATE
  Eigen3::Eigen
  TBB:tbb
  )

# Set the library version
set_target_properties(InstantMeshes PROPERTIES VERSION ${PROJECT_VERSION})
# Set .so major version so that libInstantMeshes.so.1 will be a symlink to libInstantMeshes.so.1.0.0
set_target_properties(${LIBRARY_NAME} PROPERTIES SOVERSION ${PROJECT_VERSION_MAJOR})

# Install library binaries
install(TARGETS InstantMeshes
  RUNTIME DESTINATION ${BIN_DIR}
  LIBRARY DESTINATION ${LIB_DIR}
  ARCHIVE DESTINATION ${LIB_DIR}
  )

# Local Variables:
# tab-width: 8
# mode: cmake
# indent-tabs-mode: t
# End:
# ex: shiftwidth=2 tabstop=8
