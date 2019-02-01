load('//:subdir_glob.bzl', 'subdir_glob')
load('//:buckaroo_macros.bzl', 'buckaroo_deps_from_package')

linux_deps = \
  buckaroo_deps_from_package('github.com/buckaroo-pm/openssl') + \
  buckaroo_deps_from_package('github.com/buckaroo-pm/host-dl')

macos_deps = \
  buckaroo_deps_from_package('github.com/buckaroo-pm/openssl')

cxx_library(
  name = 'jwt-cpp',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('src/include', 'jwt/**/*.hpp'),
    ('src/include', 'jwt/**/*.h'),
  ]),
  headers = subdir_glob([
    ('src/include', 'private/**/*.h'),
  ]),
  srcs = glob([
    'src/**/*.cpp',
  ]),
  platform_deps = [
    ('linux.*', linux_deps),
    ('macos.*', macos_deps),
  ],
  visibility = [
    'PUBLIC',
  ],
)
