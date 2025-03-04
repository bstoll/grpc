cc_binary(
    name = "greeter_server",
    srcs = ["greeter_server.cc"],
    defines = ["IMPORT_PREFIXES"],
    deps = [
        "@com_google_absl//absl/flags:flag",
        "@com_google_absl//absl/flags:parse",
        "@com_google_absl//absl/strings:str_format",
        "@grpc//:grpc++",
        "@grpc//:grpc++_reflection",
        "@grpc//examples/cpp/prefixes:service_cc_grpc",
    ],
)

cc_binary(
    name = "greeter_server_direct",
    srcs = ["greeter_server.cc"],
    deps = [
        "@com_google_absl//absl/flags:flag",
        "@com_google_absl//absl/flags:parse",
        "@com_google_absl//absl/strings:str_format",
        "@grpc//:grpc++",
        "@grpc//:grpc++_reflection",
        "@grpc//examples/cpp/prefixes:service_proto_direct",
    ],
)
