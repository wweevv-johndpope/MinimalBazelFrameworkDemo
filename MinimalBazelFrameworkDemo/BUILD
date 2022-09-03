load("@build_bazel_rules_apple//apple:ios.bzl", "ios_application")
load("@Plist//build-system/ios-utils:plist_fragment.bzl", "plist_fragment")
load("@build_bazel_rules_swift//swift:swift.bzl", "swift_library")
swift_library(
    name = "MinimalBazelFrameworkDemo_swift",
    module_name = "MinimalBazelFrameworkDemo",
    srcs = [
        "//MinimalBazelFrameworkDemo:ViewController.swift",
        "//MinimalBazelFrameworkDemo:AppDelegate.swift",
        "//MinimalBazelFrameworkDemo:SceneDelegate.swift",
    ],
    deps = [
        # Framework TODO (swift_library/objc_library)
    ],
    visibility = [
        "//visibility:private",
    ],
)
alias(
    name = "MinimalBazelFrameworkDemo_library",
    actual = "MinimalBazelFrameworkDemo_swift",
    visibility = [
        "//visibility:public",
    ],
)
plist_fragment(
    name = "plist_file",
    extension = "plist",
    template = '''
    <key>UIApplicationSceneManifest</key>
    <dict>
    <key>UIApplicationSupportsMultipleScenes</key>
    <false/>
    <key>UISceneConfigurations</key>
    <dict>
        <key>UIWindowSceneSessionRoleApplication</key>
        <array>
            <dict>
                <key>UISceneConfigurationName</key>
                <string>Default Configuration</string>
                <key>UISceneDelegateClassName</key>
                <string>$(MinimalBazelFrameworkDemo).SceneDelegate</string>
                <key>UISceneStoryboardFile</key>
                <string>Main</string>
            </dict>
        </array>
    </dict>
    </dict>
    <key>CFBundlePackageType</key>
    <string>APPL</string>
    <key>CFBundleShortVersionString</key>
    <string>1.0</string>
    <key>CFBundleVersion</key>
    <string>1</string>
    <key>PRODUCT_MODULE_NAME</key>
    <string>MinimalBazelFrameworkDemo</string>
    ''',
    visibility = [
        "//visibility:private",
    ],
)
plist_fragment(
    name = "plist_auto",
    extension = "plist",
    template = '''
    <key>UIApplicationSupportsIndirectInputEvents</key>
    <true/>
    <key>UILaunchStoryboardName</key>
    <string>LaunchScreen</string>
    <key>UIMainStoryboardFile</key>
    <string>Main</string>
    <key>UISupportedInterfaceOrientations~iPad</key>
    <array>
        <string>UIInterfaceOrientationPortrait</string>
        <string>UIInterfaceOrientationPortraitUpsideDown</string>
        <string>UIInterfaceOrientationLandscapeLeft</string>
        <string>UIInterfaceOrientationLandscapeRight</string>
    </array>
    <key>UISupportedInterfaceOrientations~iPhone</key>
    <array>
        <string>UIInterfaceOrientationPortrait</string>
        <string>UIInterfaceOrientationLandscapeLeft</string>
        <string>UIInterfaceOrientationLandscapeRight</string>
    </array>
    ''',
    visibility = [
        "//visibility:private",
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
ios_application(
    name = "MinimalBazelFrameworkDemo",
    bundle_id = "demo.com.sample.MinimalBazelFrameworkDemo",
    families = [
        "iphone",
        "ipad",
    ],
    minimum_os_version = "15.2",
    infoplists = [
        ":plist_file",
        ":plist_auto",
        ":plist_default",
    ],
    launch_storyboard = ":Base.lproj/LaunchScreen.storyboard",
    deps = [
        ":MinimalBazelFrameworkDemo_library",
    ],
    # frameworks = None,
    # sdk_frameworks = None,
    resources = [
        "//MinimalBazelFrameworkDemo:Base.lproj/LaunchScreen.storyboard",
        "//MinimalBazelFrameworkDemo:Assets.xcassets",
        "//MinimalBazelFrameworkDemo:Base.lproj/Main.storyboard",
    ],
    visibility = [
        "//visibility:public",
    ],
)