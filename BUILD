load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")
load("@bazel_gazelle//:def.bzl", "gazelle")

gazelle(
    name = "gazelle",
    prefix = "github.com/antonovvk/go-xgboost",
)

go_library(
    name = "go_default_library",
    srcs = ["booster.go"],
    importpath = "github.com/antonovvk/go-xgboost",
    visibility = ["//visibility:public"],
    deps = ["//core:go_default_library"],
)

go_test(
    name = "go_default_test",
    srcs = ["booster_test.go"],
    embed = [":go_default_library"],
    deps = ["//core:go_default_library"],
)
