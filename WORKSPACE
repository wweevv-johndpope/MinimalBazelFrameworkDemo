load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
# rules_apple
http_archive(
    name = "build_bazel_rules_apple",
    # sha256 = "",
    url = "https://github.com/bazelbuild/rules_apple/releases/download/1.0.1/rules_apple.1.0.1.tar.gz",
)

load(
    "@build_bazel_rules_apple//apple:repositories.bzl",
    "apple_rules_dependencies",
)

apple_rules_dependencies()

load(
    "@build_bazel_rules_swift//swift:repositories.bzl",
    "swift_rules_dependencies",
)

swift_rules_dependencies()

load(
    "@build_bazel_rules_swift//swift:extras.bzl",
    "swift_rules_extra_dependencies",
)

swift_rules_extra_dependencies()

load(
    "@build_bazel_apple_support//lib:repositories.bzl",
    "apple_support_dependencies",
)

apple_support_dependencies()

# rules_pods
http_archive(
    name = "rules_pods",
    urls = ["https://github.com/pinterest/PodToBUILD/releases/download/4.1.0-412495/PodToBUILD.zip"],
    # sha256 = "",
)

load("@rules_pods//BazelExtensions:workspace.bzl", "new_pod_repository")

load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")
git_repository(
    name = "Plist",
    commit = "259ca0a5d77833728c18fa6365285559ce8cc0bf",
    remote = "https://github.com/imWildCat/MinimalBazelFrameworkDemo",
)

http_archive(
    name = "rules_pods",
    urls = ["https://github.com/pinterest/PodToBUILD/releases/download/4.1.0-412495/PodToBUILD.zip"],
)
# Load the new_pod_repository macro - needed for `WORKSPACE` usage
load("@rules_pods//BazelExtensions:workspace.bzl", "new_pod_repository")

