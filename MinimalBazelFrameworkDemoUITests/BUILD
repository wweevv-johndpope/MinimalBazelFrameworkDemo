load("@Plist//build-system/ios-utils:plist_fragment.bzl", "plist_fragment")
load("@build_bazel_rules_swift//swift:swift.bzl", "swift_library")
swift_library(
    name = "MinimalBazelFrameworkDemoUITests_swift",
    module_name = "MinimalBazelFrameworkDemoUITests",
    srcs = [
        "//MinimalBazelFrameworkDemoUITests:MinimalBazelFrameworkDemoUITests.swift",
        "//MinimalBazelFrameworkDemoUITests:MinimalBazelFrameworkDemoUITestsLaunchTests.swift",
    ],
    deps = [
        # Framework TODO (swift_library/objc_library)
        "//MinimalBazelFrameworkDemo:MinimalBazelFrameworkDemo_library",
    ],
    visibility = [
        "//visibility:private",
    ],
)
alias(
    name = "MinimalBazelFrameworkDemoUITests_library",
    actual = "MinimalBazelFrameworkDemoUITests_swift",
    visibility = [
        "//visibility:public",
    ],
)
plist_fragment(
    name = "plist_default",
    extension = "plist",
    template = '''
    <key>CFBundleDevelopmentRegion</key>
    <string>$(DEVELOPMENT_LANGUAGE)</string>
    <key>CFBundleExecutable</key>
    <string>$(EXECUTABLE_NAME)</string>
    <key>CFBundleIdentifier</key>
    <string>$(PRODUCT_BUNDLE_IDENTIFIER)</string>
    <key>CFBundleName</key>
    <string>$(PRODUCT_NAME)</string>
    <key>CFBundlePackageType</key>
    <string>$(PRODUCT_BUNDLE_PACKAGE_TYPE)</string>
    <key>CFBundleShortVersionString</key>
    <string>1.0</string>
    <key>CFBundleVersion</key>
    <string>1</string>
    ''',
    visibility = [
        "//visibility:private",
    ],
)