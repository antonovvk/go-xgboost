load("@bazel_tools//tools/build_defs/repo:git.bzl", "new_git_repository")
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

new_git_repository(
    name = "gtest",
    build_file = "@//:gtest.BUILD",
    remote = "https://github.com/google/googletest",
    tag = "release-1.8.0",
)

new_git_repository(
    name = "dmlccore",
    build_file = "@//:dmlccore.BUILD",
    commit = "c54b27e4355333732cd2f6a20c6b37e6900b3a89",
    remote = "https://github.com/dmlc/dmlc-core",
)

new_git_repository(
    name = "rabit",
    build_file = "@//:rabit.BUILD",
    commit = "493ad834a1102fcf355a250a3bd08937066cda08",
    remote = "https://github.com/dmlc/rabit",
)

new_git_repository(
    name = "xgboost",
    build_file = "@//:xgboost.BUILD",
    commit = "7b65698187acb5163a4972beaf54d9e6b822beed",
    remote = "https://github.com/dmlc/xgboost",
)

http_archive(
    name = "io_bazel_rules_go",
    urls = [
        "https://storage.googleapis.com/bazel-mirror/github.com/bazelbuild/rules_go/releases/download/v0.20.2/rules_go-v0.20.2.tar.gz",
        "https://github.com/bazelbuild/rules_go/releases/download/v0.20.2/rules_go-v0.20.2.tar.gz",
    ],
    sha256 = "b9aa86ec08a292b97ec4591cf578e020b35f98e12173bbd4a921f84f583aebd9",
)

http_archive(
    name = "bazel_gazelle",
    urls = [
        "https://storage.googleapis.com/bazel-mirror/github.com/bazelbuild/bazel-gazelle/releases/download/v0.19.1/bazel-gazelle-v0.19.1.tar.gz",
        "https://github.com/bazelbuild/bazel-gazelle/releases/download/v0.19.1/bazel-gazelle-v0.19.1.tar.gz",
    ],
    sha256 = "86c6d481b3f7aedc1d60c1c211c6f76da282ae197c3b3160f54bd3a8f847896f",
)

#~ load("@bazel_gazelle//:deps.bzl", "go_repository")

load("@io_bazel_rules_go//go:deps.bzl", "go_rules_dependencies", "go_register_toolchains")
go_rules_dependencies()
go_register_toolchains()

load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies")
gazelle_dependencies()
