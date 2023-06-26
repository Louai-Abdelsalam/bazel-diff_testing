genrule(
    name = "nonTestDepOneLevelTwo",
    outs = ["outputA.txt"],
    cmd = "echo 'someContent' > $@",
    visibility = ["//visibility:public"],
)

sh_test(
    name = "testDepOneLevelTwo",
    srcs = [
        ":testDepOneLevelTwo.sh"
    ],
    tags = ["manual"],
    visibility = ["//visibility:public"],
)

sh_test(
    name = "testDepTwoLevelTwo",
    srcs = [
        ":testDepTwoLevelTwo.sh"
    ],
    visibility = ["//visibility:public"],
)