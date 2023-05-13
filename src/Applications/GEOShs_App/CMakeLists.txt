ecbuild_add_executable (
  TARGET GEOShs.x
  SOURCES GEOShs.F90
  LIBS GEOSagcm_GridComp esmf OpenMP::OpenMP_Fortran
  )
target_include_directories (GEOShs.x PUBLIC $<BUILD_INTERFACE:${MAPL_SOURCE_DIR}/include>)
target_link_libraries (GEOShs.x -fopenacc -foffload="-lgfortran -lgomp -lm" -foffload=nvptx-none)
