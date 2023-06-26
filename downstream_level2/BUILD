genrule(
    name = "nonTestReverseDepOneLevelTwo",
    outs = ["outputA.txt"],
    cmd = "echo 'someContent' > $@",
    visibility = ["//visibility:public"],
)

sh_test(
    name = "testReverseDepOneLevelTwo",
    data = [
        "//downstream_level1:testReverseDepTwoLevelOne",
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