genrule(
    name = "nonTestDepOneLevelOne",
    outs = ["outputA.txt"],
    cmd = "echo 'someContent' > $@",
    visibility = ["//visibility:public"],
)

sh_test(
    name = "testDepOneLevelOne",
    srcs = [
        "testDepOneLevelOne.sh"
    ],
    tags = ["manual"],
    visibility = ["//visibility:public"],
)

sh_test(
    name = "testDepTwoLevelOne",
    data = [
        "//upstream_level2:nonTestDepOneLevelTwo",
        "//upstream_level2:testDepOneLevelTwo",
        "//upstream_level2:testDepTwoLevelTwo",
    ],
    srcs = [
        ":testDepTwoLevelOne.sh"
    ],
    visibility = ["//visibility:public"],
)