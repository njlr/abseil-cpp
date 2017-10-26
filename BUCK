include_defs('//BUCKAROO_DEPS')

cxx_library(
  name = 'abseil',
  header_namespace = 'absl',
  exported_headers = subdir_glob([
    ('absl', '**/*.h'),
    ('absl', '**/*.inc'),
  ]),
  srcs = glob([
    'absl/**/*.cc',
  ], excludes = glob([
    'absl/synchronization/internal/mutex_nonprod.cc',
    'absl/**/*_test.cc',
    'absl/**/*_test_*.cc',
  ])),
  licenses = [
    'LICENSE',
  ],
  deps = BUCKAROO_DEPS,
  visibility = [
    'PUBLIC',
  ],
)

cxx_test(
  name = 'tests',
  header_namespace = '',
  srcs = glob([
    'absl/**/*_test.cc',
    'absl/**/*_test_*.cc',
  ]),
  preprocessor_flags = [
    '-DABSL_MALLOC_EXTENSION_TEST_ALLOW_MISSING_EXTENSION=1',
  ],
  deps = [
    ':abseil',
  ],
)
