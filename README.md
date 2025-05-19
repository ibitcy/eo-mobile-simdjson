<p align="center">
    <a href="https://jitpack.io/#ibitcy/eo-mobile-simdjson"><img src="https://jitpack.io/v/ibitcy/eo-mobile-simdjson.svg"/></a>
    <a href="http://cocoapods.org/pods/eo-mobile-simdjson"><img src="https://img.shields.io/cocoapods/v/eo-mobile-simdjson.svg?style=flat" alt="Version"/></a>
</p>


# eo-mobile-simdjson 3.2.2

Easy to use solution for including [Simdjson](https://github.com/simdjson/simdjson) into your Android (using prefab) and iOS projects/libraries

# Android

### Before you start

This package made for using it with Gradle's "prefab" dependencies system.

So it's better to start with reading more about it [here](https://developer.android.com/studio/build/dependencies?buildsystem=cmake#native-dependencies-with-agp) or [here](https://github.com/android/ndk-samples/tree/main/prefab).

### How to

1. Add dependencies to your build.gradle:
```gradle
repositories {
    maven { url 'https://jitpack.io' }
}
..
dependencies {
    ..
    implementation 'com.github.ibitcy:eo-mobile-simdjson:3.2.2'
    ..
}
```
2. Add this code pieces to your CMakeLists.txt:
```cmake
find_package(simdjson REQUIRED CONFIG)
..
target_link_libraries(
        your_library_name
        ..
        simdjson::simdjson
        ..
)
```
3. Build! 🎉🎉🎉

# iOS

1. Add this string to your Podfile

```ruby
pod 'eo-mobile-simdjson'
```
2. run `pod install` in your project's directory
3. Build! 🎉🎉🎉

# Finally

Now you can use it, including like a dynamic library:
```C++
#include <simdjson/simdjson.h>
```
