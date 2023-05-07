# FlamingoSample
Keep up to date with Android development.

## Explore the Jetpack libraries by type
Search Jetpack libraries in [Jetpack homepage](https://developer.android.google.cn/jetpack/androidx/explorer).
> English language pages should show newer library version than the Chinese.

## Explore dependencies by code completion
Type a library name in module dependencies block, libraries with the latest version will be suggested.
> New version dependencies generally require new kotlin version, find latest kotlin version from [Kotlin website](https://kotlinlang.org/docs/home.html).

## Android Studio and AGP compatibility
Each version of Android Studio requires specific versions of AGP, pay especially attention to the maximun supported version from [AGP releases](https://developer.android.google.cn/build/releases/gradle-plugin#android_gradle_plugin_and_android_studio_compatibility).
> AGP version supported by Flamingo is 3.2-8.0. Patch releases like 8.0.x are also included.

## AGP and the Minimum required Gradle version
Find the minimum supported version from [Update gradle](https://developer.android.google.cn/build/releases/gradle-plugin#updating-gradle) section and the version from [Gradle website](https://gradle.org/releases/).
> AGP 8.0 requires the Gradle version not older than Gradle 8.0.

## Understanding build.gradle
A Project is an ExtensionAware Object that has an ExtensionContainer field implemented as ```Map<String, Object>```.

```android``` block in build.gradle file represents an extension of type ```BaseAppModuleExtension``` created and added to the project in ```AppPlugin```.

```BaseAppModuleExtension``` has fields like ```defaultConfig```, ```buildTypes``` etc.,```buildFeatures``` and ```namespace``` are indirectly implemented by extensions when they implement the new public extension interfaces via delegates.
> To view AGP source code, add the following dependencies to the app module build.gradle:  
> implementation gradleApi()  
> implementation 'com.android.tools.build:gradle:8.0.1'