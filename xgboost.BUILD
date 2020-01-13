cc_library(
    name = "xgboost",
    srcs = glob(
        [
            "src/**/*.cc",
            "src/*.cc",
        ],
        exclude = ["src/cli_main.cc"]
    ),
    hdrs = glob([
        "include/xgboost/*.h",
        "src/**/*.h",
    ]),
    includes = [
        "include",
        "src",
    ],
    copts = [
        "-std=c++11",
        "-fopenmp",
        "-Wall",
    ],
    deps = [
        "@dmlccore//:dmlccore",
        "@rabit//:rabit",
    ],
    linkopts =[
        "-lgomp",
    ],
    visibility = ["//visibility:public"],
)

cc_binary(
    name = "cli",
    srcs = ["src/cli_main.cc"],
    copts = [
        "-std=c++11",
        "-Wall",
    ],
    linkopts = [
        "-lpthread",
    ],
    deps = [
        ":xgboost",
    ],
    visibility = ["//visibility:private"],
)

cc_test(
    name = "unittest",
    srcs = glob(
        [
            "tests/cpp/**/*.h",
            "tests/cpp/**/*.cc",
        ],
        exclude = [
            "tests/cpp/objective/test_multiclass_obj.cc",
        ],
    ),
    copts = [
        "-Iexternal/gtest/googletest/include",
    ],
    deps = [
        "@gtest//:main",
        ":xgboost",
    ],
    linkopts = [
        "-lm",
    ],
)
