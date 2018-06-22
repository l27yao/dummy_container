licenses(["notice"])  # Apache 2.0

package(default_visibility = ["//visibility:public"])

load("@io_bazel_rules_docker//container:image.bzl", "container_image")

container_image(
    name = "test",
    base = "@ubuntu16_04//image",
    cmd = [
        "/bin/sh",
        "-c",
        "/bin/bash",
    ],
    files = ["@my_tar//file"],
)
