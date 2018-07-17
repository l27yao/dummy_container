licenses(["notice"])  # Apache 2.0

package(default_visibility = ["//visibility:public"])

load("@io_bazel_rules_docker//container:image.bzl", "container_image")

load("@io_bazel_rules_docker//contrib:test.bzl", "container_test")

container_image(
    name = "dummy",
    base = "@ubuntu16_04//image",
    cmd = [
        "/bin/sh",
        "-c",
        "/bin/bash",
    ],
    tars = ["@my_tar//file"],
)

container_test(
    name = "dummy-test",
    configs = [
        ":dummy-ubuntu16_04.yaml",
    ],
    image = ":dummy",
)
