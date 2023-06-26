genrule(
    name = "nonTestReverseDepOneLevelOne",
    outs = ["outputA.txt"],
    cmd = "echo 'someContent' > $@",
    visibility = ["//visibility:public"],
)

sh_test(
    name = "testReverseDepOneLevelOne",
    srcs = [
        "testReverseDepOneLevelOne.sh"
    ],
    tags = ["manual"],
    visibility = ["//visibility:public"],
)

sh_test(
    name = "testReverseDepTwoLevelOne",
    data = [
        "//upstream_level1:testDepOneLevelOne",
        "//main:testTwo",
    ],
    srcs = [
        ":testReverseDepTwoLevelOne.sh"
    ],
    visibility = ["//visibility:public"],
)