load("@rules_java//java:defs.bzl", "java_binary"    visibility = ["//visibility:public"],
)

java_binary(
    name = "bazel-diff",
    main_class = "com.bazel_diff.Main",
    runtime_data = ["@bazel_diff//jar"],
    visibility = ["//visibility:public"],
)
