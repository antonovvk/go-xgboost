cc_library(
    name = "rabit",
    srcs = glob(
        [
            "include/dmlc/*.h",
            "include/rabit/internal/*.h",
            "src/*.h",
            "src/allreduce_base.cc",
            "src/allreduce_robust.cc",
            "src/c_api.cc",
            "src/engine.cc",
        ],
    ),
    hdrs = glob([
        "include/rabit/*.h",
    ]),
    includes = [
        "include",
    ],
    copts = [
        "-std=c++11",
        "-Wall",
    ],
    visibility = ["//visibility:public"],
)
