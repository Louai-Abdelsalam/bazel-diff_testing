workspace(name = "bazel-diff_testing")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive", "http_jar")

http_jar(
    name = "bazel_diff",
    sha256 = "9c4546623a8b9444c06370165ea79a897fcb9881573b18fa5c9ee5c8ba0867e2",
    urls = [
        "https://github.com/Tinder/bazel-diff/releases/download/4.3.0/bazel-diff_deploy.jar",
    ],
)

http_archive(
    name = "aws_sam",
    build_file_content = "exports_files([\"sam_bin\"])\n",
    patch_cmds = [
        "./install --install-dir $(pwd)/aws_sam_installation_dir",
        "ln -s aws_sam_installation_dir/current/dist/sam sam_bin",
    ],
    # sha256 = "24aa5893e35ce370b92b730fe163d902d248bdef4e3513eb3810bc6ff91a4efd",
    sha256 = "616511d24b422ed92c51b083657af63bc58b52e28c030ee228ecce0881a7a78d",
    urls = [
        # "https://github.com/aws/aws-sam-cli/releases/download/v1.73.0/aws-sam-cli-linux-x86_64.zip",
        "https://github.com/aws/aws-sam-cli/releases/download/v1.89.0/aws-sam-cli-linux-x86_64.zip"
    ],
)
