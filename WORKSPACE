# rules sh

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
http_archive(
    name = "rules_sh",
    sha256 = "d668bb32f112ead69c58bde2cae62f6b8acefe759a8c95a2d80ff6a85af5ac5e",
    strip_prefix = "rules_sh-0.3.0",
    urls = ["https://github.com/tweag/rules_sh/archive/v0.3.0.tar.gz"],
)
load("@rules_sh//sh:repositories.bzl", "rules_sh_dependencies")
rules_sh_dependencies()


# rules nixpkgs

COMMIT="ea5c0bbcc9189473b95f22d3febddb5e56842932"

load(
    "@bazel_tools//tools/build_defs/repo:http.bzl",
    "http_archive",
)

http_archive(
    name = "io_tweag_rules_nixpkgs",
    strip_prefix = "rules_nixpkgs-" + COMMIT,
    urls = ["https://github.com/tweag/rules_nixpkgs/archive/" + COMMIT + ".tar.gz"],
    sha256 = "be39febe011cf12801dc5b7fda261969fdb5d0e9b67f898e790b7888d042ee93",
)

load("@io_tweag_rules_nixpkgs//nixpkgs:repositories.bzl", "rules_nixpkgs_dependencies")
rules_nixpkgs_dependencies()

load("@io_tweag_rules_nixpkgs//nixpkgs:nixpkgs.bzl", "nixpkgs_git_repository", "nixpkgs_package", "nixpkgs_cc_configure")

load("@io_tweag_rules_nixpkgs//toolchains/posix:posix.bzl", "nixpkgs_sh_posix_configure")


load(
    "@io_tweag_rules_nixpkgs//nixpkgs:nixpkgs.bzl",
    "nixpkgs_git_repository",
    "nixpkgs_local_repository",
    "nixpkgs_package",
)

nixpkgs_git_repository(
    name = "nixpkgs",
    revision = "22.05", # Any tag or commit hash
    # sha256 = "" # optional sha to verify package integrity!
)

nixpkgs_package(
    name = "postgresql",
    attribute_path = "postgresql",
    repositories = {"nixpkgs": "@nixpkgs//:default.nix"},
)




# nixpkgs_sh_posix_configure(
#   name = "pkgs",
#   packages = ["postgres"],
# )
# 
# 
# load("@rules_sh//sh:posix.bzl", "sh_posix_configure")
# sh_posix_configure()
