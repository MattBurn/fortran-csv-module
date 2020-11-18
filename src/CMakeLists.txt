set(dir "${CMAKE_CURRENT_SOURCE_DIR}")

list(
  APPEND srcs
  "${dir}/csv_kinds.f90"
  "${dir}/csv_module.f90"
  "${dir}/csv_parameters.f90"
  "${dir}/csv_utilities.f90"
)

set(srcs "${srcs}" PARENT_SCOPE)
