cc_library(
    name = "dmlccore",
    srcs = glob(
        [
            "src/**/*.cc",
            "src/**/*.h",
            "src/*.cc",
        ],
        exclude = [
            "src/io/azure_filesys.cc",
            "src/io/hdfs_filesys.cc",
            "src/io/s3_filesys.cc",
        ],
    ),
    hdrs = glob([
        "include/dmlc/*.h",
    ]),
    includes = [
        "include",
    ],
    copts = [
        "-std=c++11",
        "-Wall",
        "-fopenmp",
        "-DDMLC_USE_HDFS=0",
        "-DDMLC_USE_S3=0",
        "-DDMLC_USE_AZURE=0",
    ],
    linkopts = [
        "-lgomp",
    ],
    visibility = ["//visibility:public"],
)

cc_test(
    name = "unittest",
    srcs = glob([
        "test/unittest/*.cc",
    ]),
    copts = [
        "-Iexternal/gtest/googletest/include",
    ],
    deps = [
        "@gtest//:main",
        ":dmlccore",
    ],
    linkopts = [
        "-lm",
    ],
)
