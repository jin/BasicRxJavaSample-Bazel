Room & RxJava Sample built with Bazel
=====================

This is Android Architecture Components' [BasicRxJavaSample](https://github.com/googlesamples/android-architecture-components/tree/master/BasicRxJavaSample) project adapted to build with Bazel.

## Build

```
$ bazel build //:app
```

## Deploy

```
$ bazel mobile-install //:app

# or

$ adb install bazel-bin/app.apk
```
