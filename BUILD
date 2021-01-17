load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library")
load("@bazel_gazelle//:def.bzl", "gazelle")

# gazelle:proto disable_global
# gazelle:prefix github.com/button/btngo
gazelle(
    name = "gazelle",
    command = "fix",
    external = "vendored",
)

load("@rules_java//java:defs.bzl", "java_binary")

java_binary(
    name = "bazel-diff",
    main_class = "com.bazel_diff.BazelDiff",
    runtime_deps = ["@bazel_diff//jar"],
)

go_library(
    name = "repro_lib",
    srcs = ["repro.go"],
    importpath = "github.com/jonahgeorge/bazel-diff-repro",
    visibility = ["//visibility:private"],
)

go_binary(
    name = "repro",
    embed = [":repro_lib"],
    visibility = ["//visibility:public"],
)
