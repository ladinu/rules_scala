load("//scala:scala.bzl", "scala_library_for_plugin_bootstrapping")
load("//scala:scala_cross_version.bzl", "version_suffix")
load("@io_bazel_rules_scala_config//:config.bzl", "SCALA_VERSION")

scala_library_for_plugin_bootstrapping(
    name = "dep_reporting_compiler",
    srcs = ["@scala_compiler_source%s//:src" % version_suffix(SCALA_VERSION)],
    scalac_jvm_flags = ["-Xmx128M"],  # fixme - workaround for a failing test
    visibility = ["//visibility:public"],
    deps = ["//scala/private/toolchain_deps:scala_compile_classpath"],
)
