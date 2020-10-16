project(
  'fortran-csv-module',
  'fortran',
  version: '0.2.0',
  meson_version: '>=0.53',
  default_options: [
    'buildtype=debugoptimized',
    'default_library=both',
  ],
)
install = not (meson.is_subproject() and get_option('default_library') == 'static')

# Collect source of the project
srcs = []
subdir('src')

# TOML-Fortran library target
csv_lib = library(
  meson.project_name(),
  sources: srcs,
  version: meson.project_version(),
  install: install,
)

# Export dependency for other projects and test suite
csv_inc = csv_lib.private_dir_include()
csv_dep = declare_dependency(
  link_with: csv_lib,
  include_directories: csv_inc,
)

if install
  pkg = import('pkgconfig')
  pkg.generate(
    csv_lib,
    description: 'A CSV parser implementation for data deserialization in Fortran',
  )
endif
