load("@bazel_gazelle//:def.bzl", "gazelle")
load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library")

# gazelle:prefix github.com/paina/protoc-gen-validate
# gazelle:exclude tests
# gazelle:exclude example-workspace
# gazelle:exclude validate/validate.h
# gazelle:go_naming_convention import_alias
gazelle(name = "gazelle")

go_binary(
    name = "protoc-gen-validate",
    embed = [":protoc-gen-validate_lib"],
    importpath = "github.com/paina/protoc-gen-validate",
    visibility = ["//visibility:public"],
)

go_library(
    name = "protoc-gen-validate_lib",
    srcs = ["main.go"],
    importpath = "github.com/paina/protoc-gen-validate",
    visibility = ["//visibility:private"],
    deps = [
        "//module",
        "@org_golang_google_protobuf//types/pluginpb",
        "@com_github_lyft_protoc_gen_star//:protoc-gen-star",
        "@com_github_lyft_protoc_gen_star//lang/go",
    ],
)
