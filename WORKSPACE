workspace(name = "experiment")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "io_bazel_rules_docker",
    sha256 = "5466861acd1e0a2afe745fdf383e5a4b5e06d19e571d49d252828cb2f2de13cb",
    strip_prefix = "rules_docker-e325ffbf6508fe4cbaa3f5a0b09898f15e912d6a",
    urls = ["https://github.com/bazelbuild/rules_docker/archive/e325ffbf6508fe4cbaa3f5a0b09898f15e912d6a.tar.gz"],
)

load(
    "@io_bazel_rules_docker//container:container.bzl",
    "container_pull",
    container_repositories = "repositories",
)

container_repositories()

load(
    "@io_bazel_rules_docker//contrib:test.bzl",
    "container_test",
)

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "4b14d8dd31c6dbaf3ff871adcd03f28c3274e42abc855cb8fb4d01233c0154dc",
    urls = ["https://github.com/bazelbuild/rules_go/releases/download/0.10.1/rules_go-0.10.1.tar.gz"],
)

load("@io_bazel_rules_go//go:def.bzl", "go_register_toolchains", "go_rules_dependencies")

go_rules_dependencies()

go_register_toolchains()

load(
    "//:pins.bzl",
    "TAR_REVISION",
    "TAR_SHA256",
    "UBUNTU16_04",
)

container_pull(
    name = "ubuntu16_04",
    digest = UBUNTU16_04,
    registry = "gcr.io",
    repository = "cloud-marketplace/google/ubuntu16_04",
)

http_file(
    name = "my_tar",
    sha256 = TAR_SHA256,
    urls = ["https://storage.googleapis.com/quickstart-lei/test_" + TAR_REVISION + ".tar.gz"],
)
