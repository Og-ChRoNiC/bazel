package(default_visibility = ["//visibility:public"])

load("@rules_cc//cc:defs.bzl", "objc_library")

# Files which shouldn't be publicly visible and dependencies of all objc_* or ios_* rules shouldn't be in this package.
exports_files(glob(["**"]))

filegroup(
    name = "srcs",
    srcs = glob(["**"]),
)

sh_binary(
    name = "libtool",
    srcs = [":libtool.sh"],
    data = [
        ":make_hashed_objlist.py",
        ":xcrunwrapper",
    ],
)

sh_binary(
    name = "xcrunwrapper",
    srcs = [":xcrunwrapper.sh"],
)

filegroup(
    name = "xctest_infoplist",
    srcs = ["XCTest-Info.plist"],
)

filegroup(
    name = "gcov",
    srcs = [":gcov_stub"],
)

filegroup(
    name = "mcov",
    srcs = [":mcov_stub"],
)

xcode_config(
    name = "host_xcodes",
)

filegroup(
    name = "j2objc_dead_code_pruner",
    srcs = ["j2objc_dead_code_pruner.py"],
)

objc_library(
    name = "dummy_lib",
    srcs = [
        "objc_dummy.mm",
    ],
)

filegroup(
    name = "protobuf_compiler_wrapper",
    srcs = ["protobuf_compiler_wrapper.sh"],
)

filegroup(
    name = "protobuf_compiler",
    srcs = ["protobuf_compiler.py"],
)

filegroup(
    name = "protobuf_compiler_support",
    srcs = ["protobuf_support"],
)

filegroup(
    name = "protobuf_well_known_types",
    srcs = ["dummy.proto"],
)

# Intentionally empty
filegroup(
    name = "header_scanner",
    srcs = [],
)
