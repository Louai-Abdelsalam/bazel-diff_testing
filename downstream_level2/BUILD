genrule(
    name = "nonTestReverseDepOneLevelTwo",
    outs = ["outputA.txt"],
    cmd = "echo 'someContent' > $@",
    visibility = ["//visibility:public"],
)

sh_test(
    name = "testReverseDepOneLevelTwo",
    data = [
        "//upstream_level2:testDepOneLevelTwo",
    ],
    srcs = [
        "testReverseDepOneLevelTwo.sh"
    ],
    tags = ["manual"],
    visibility = ["//visibility:public"],
)

sh_test(
    name = "testReverseDepTwoLevelTwo",
    data = [
        "//downstream_level1:testReverseDepTwoLevelOne",
    ],
    srcs = [
        "testReverseDepTwoLevelTwo.sh"
    ],
    visibility = ["//visibility:public"],
)