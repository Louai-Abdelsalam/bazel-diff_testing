load("@rules_java//java:defs.bzl", "java_binary")

java_binary(
    name = "bazel-diff",
    main_class = "com.bazel_diff.Main",
    runtime_deps = ["@bazel_diff//jar"],
    visibility = ["//visibility:public"],
)

genrule(
    name = "tester_of_external_repos",
    srcs = ["@aws_sam//:sam_bin"],
    outs = [
        "samVersion.txt",
    ],
    cmd = "$(location @aws_sam//:sam_bin) --version > $@",
    visibility = ["//visibility:public"],
)
