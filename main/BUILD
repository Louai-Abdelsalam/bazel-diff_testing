genrule(
    name = "nonTestOne",
    outs = ["outputA.txt"],
    cmd = "echo 'someContent' > $@",
    tags = ["manual"],
    visibility = ["//visibility:public"],
)

genrule(
    name = "nonTestTwo",
    srcs = ["outputA.txt"],
    outs = ["outputB.txt"],
    cmd = "cat $< > $@ && echo 'someMoreContent' >> $@",
    tags = ["ok"],
    visibility = ["//visibility:public"],
)

sh_test(
    name = "testOne",
    data = [
        "//upstream_level1:nonTestDepOneLevelOne",
    ],
    srcs = [
        ":testOne.sh"
    ],
    tags = ["ok"],
    visibility = ["//visibility:public"],
)

sh_test(
    name = "testTwo",
    data = [
        "//upstream_level1:nonTestDepOneLevelOne",
        "//upstream_level1:testDepOneLevelOne",
        "//upstream_level1:testDepTwoLevelOne",
    ],
    srcs = [
        ":testTwo.sh",
    ],
    visibility = ["//visibility:public"],
)
