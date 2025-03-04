load("//bazel:cc_grpc_library.bzl", "cc_grpc_library")

proto_library(
    name = "service_proto",
    srcs = [
        ":service.proto",
        ":service_extra.proto",
    ],
    import_prefix = "custom/prefix",
    strip_import_prefix = "/examples/cpp/prefixes",
    deps = [
        "@com_google_protobuf//:any_proto",
    ],
)

cc_proto_library(
    name = "service_cc_proto",
    deps = [":service_proto"],
)

cc_grpc_library(
    name = "service_cc_grpc",
    srcs = [":service_proto"],
    grpc_only = True,
    visibility = ["//visibility:public"],
    deps = [":service_cc_proto"],
)

cc_binary(
    name = "greeter_server",
    srcs = ["greeter_server.cc"],
    defines = ["IMPORT_PREFIXES"],
    deps = [
        ":service_cc_grpc",
        "//:grpc++",
        "//:grpc++_reflection",
        "@com_google_absl//absl/flags:flag",
        "@com_google_absl//absl/flags:parse",
        "@com_google_absl//absl/strings:str_format",
    ],
)

cc_binary(
    name = "greeter_server_direct",
    srcs = ["greeter_server.cc"],
    deps = [
        ":service_proto_direct",
        "//:grpc++",
        "//:grpc++_reflection",
        "@com_google_absl//absl/flags:flag",
        "@com_google_absl//absl/flags:parse",
        "@com_google_absl//absl/strings:str_format",
    ],
)

proto_library(
    name = "service2_proto",
    srcs = [":service2.proto"],
    deps = [":service_proto"],
)

cc_proto_library(
    name = "service2_cc_proto",
    deps = [":service2_proto"],
)

cc_grpc_library(
    name = "service2_cc_grpc",
    srcs = [":service2_proto"],
    grpc_only = True,
    deps = [":service2_cc_proto"],
)

cc_grpc_library(
    name = "service_proto_direct",
    srcs = ["service.proto"],
    visibility = ["//visibility:public"],
    well_known_protos = True,
    deps = [],
)
