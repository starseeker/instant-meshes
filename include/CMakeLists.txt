set(IM_HDRS
  aabb.h
  adjacency.h
  batch.h
  bvh.h
  cleanup.h
  common.h
  dedge.h
  extract.h
  field.h
  hierarchy.h
  meshio.h
  meshstats.h
  normal.h
  reorder.h
  serializer.h
  smoothcurve.h
  subdivide.h
  )

# Install the top-level header files
install(FILES ${IM_HDRS} DESTINATION ${INCLUDE_DIR}/instant-meshes)

# Local Variables:
# tab-width: 8
# mode: cmake
# indent-tabs-mode: t
# End:
# ex: shiftwidth=2 tabstop=8
