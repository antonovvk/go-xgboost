load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "utils.go",
        "xgboost.go",
        "xgbooster.go",
        "xgdmatrix.go",
    ],
    cdeps = [
        "@xgboost",
    ],
    cgo = True,
    copts = ["-fopenmp -Wall"],
    importpath = "github.com/antonovvk/go-xgboost/core",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "xgboost_test.go",
        "xgdmatrix_test.go",
    ],
    embed = [":go_default_library"],
)
