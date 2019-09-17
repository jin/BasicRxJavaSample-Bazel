load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

RULES_JVM_EXTERNAL_TAG = "2.7"

RULES_JVM_EXTERNAL_SHA = "f04b1466a00a2845106801e0c5cec96841f49ea4e7d1df88dc8e4bf31523df74"

http_archive(
    name = "rules_jvm_external",
    sha256 = RULES_JVM_EXTERNAL_SHA,
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
)

load("@rules_jvm_external//:defs.bzl", "maven_install")
load("@rules_jvm_external//:specs.bzl", "maven")

maven_install(
    name = "maven",
    artifacts = [
        "androidx.appcompat:appcompat:1.0.0",
        "androidx.legacy:legacy-support-v4:1.0.0",
        "com.google.android.material:material:1.0.0",
        "androidx.lifecycle:lifecycle-runtime:2.0.0",
        "androidx.lifecycle:lifecycle-extensions:2.0.0",
        "androidx.room:room-runtime:2.1.0-alpha06",
        "androidx.room:room-rxjava2:2.1.0-alpha06",
        "io.reactivex.rxjava2:rxandroid:2.0.1",
        "io.reactivex.rxjava2:rxjava:2.1.3",

        # Annotation processors
        "androidx.lifecycle:lifecycle-compiler:2.0.0",
        "androidx.room:room-compiler:2.1.0-alpha04",
        "com.google.guava:guava:28.1-android",
    ],
    repositories = [
        "https://maven.google.com",
        "https://jcenter.bintray.com",
        "https://repo1.maven.org/maven2",
    ],
)

android_sdk_repository(name = "androidsdk")

RULES_KOTLIN_VERSION = "da1232eda2ef90d4375e2d1677b32c7ddf09e8a1"

http_archive(
    name = "io_bazel_rules_kotlin",
    sha256 = "0bbb0e5e536f0c775f37bded59d4f8cfb8556e6c3d926fcc0f58bf3489bff470",
    strip_prefix = "rules_kotlin-%s" % RULES_KOTLIN_VERSION,
    url = "https://github.com/bazelbuild/rules_kotlin/archive/%s.tar.gz" % RULES_KOTLIN_VERSION,
)

load("@io_bazel_rules_kotlin//kotlin:kotlin.bzl", "kotlin_repositories", "kt_register_toolchains")

kotlin_repositories()

kt_register_toolchains()
