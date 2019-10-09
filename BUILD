load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

package(default_visibility = ["//visibility:public"])

load("@bazel_gazelle//:def.bzl", "gazelle")

# gazelle:prefix github.com/example/app
gazelle(
    name = "gazelle",
)

go_library(
    name = "go_default_library",
    srcs = [
        "byteview.go",
        "groupcache.go",
        "http.go",
        "peers.go",
        "sinks.go",
    ],
    importpath = "github.com/example/app",
    deps = [
        "@com_github_golang_groupcache//consistenthash:go_default_library",
        "@com_github_golang_groupcache//groupcachepb:go_default_library",
        "@com_github_golang_groupcache//lru:go_default_library",
        "@com_github_golang_groupcache//singleflight:go_default_library",
        "@com_github_golang_protobuf//proto:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "byteview_test.go",
        "groupcache_test.go",
        "http_test.go",
    ],
    embed = [":go_default_library"],
    deps = [
        "@com_github_golang_groupcache//groupcachepb:go_default_library",
        "@com_github_golang_groupcache//testpb:go_default_library",
        "@com_github_golang_protobuf//proto:go_default_library",
    ],
)
