# AndroidStudioStarter
Keep dev tools up to date with each Android Studio version.

## Explore the Jetpack libraries by type
Search Jetpack libraries in [Jetpack homepage](https://developer.android.google.cn/jetpack/androidx/explorer).
> English language pages should show newer library version than the Chinese.

## Explore dependencies by code completion
Type a library name in module dependencies block, libraries with the latest version will be suggested.
> New version dependencies generally require new kotlin version, find latest kotlin version from [Kotlin website](https://kotlinlang.org/docs/home.html).

## Android Studio and AGP compatibility
Each version of Android Studio requires specific versions of AGP, pay especially attention to the maximum supported version from [AGP releases](https://developer.android.google.cn/build/releases/gradle-plugin#android_gradle_plugin_and_android_studio_compatibility).
> AGP version supported by Flamingo is 3.2-8.0. Patch releases like 8.0.x are also included.

## AGP and the Minimum required Gradle version
Find the minimum supported version from [Update gradle](https://developer.android.google.cn/build/releases/gradle-plugin#updating-gradle) section and the version from [Gradle website](https://gradle.org/releases/).
> AGP 8.0 requires the Gradle version not older than Gradle 8.0.

## Understanding build.gradle
A Project is an ExtensionAware Object that has an ExtensionContainer field implemented as ```Map<String, Object>```.

```android``` block in build.gradle file represents an extension of type ```BaseAppModuleExtension``` created and added to the project in ```AppPlugin```.

```BaseAppModuleExtension``` has fields like ```defaultConfig```, ```buildTypes``` etc.,```buildFeatures``` and ```namespace``` are indirectly implemented by extensions when they implement the new public extension interfaces via delegates.
> To view AGP source code, add the following dependencies to the app module build.gradle:  
> compileOnly gradleApi()  
> compileOnly 'com.android.tools.build:gradle:$agp'

## Groovy to Kotlin DSL Migration
Follow these steps, view [Migrating build logic from Groovy to Kotlin](https://docs.gradle.org/current/userguide/migrating_from_groovy_to_kotlin_dsl.html) for detail documentation.  
1. Searching for ' and replacing by "  
2. Disambiguating function invocations and property assignments  
3. Naming script file build.gradle.kts  
4. Configuring plugins, tasks and dependencies  
5. Creating tasks or custom configurations

Best practices:  
- Applying plugins in the [```plugins {}```](https://docs.gradle.org/current/userguide/plugins.html#sec:plugins_block) block  
- Putting local build logic in the build’s [buildSrc](https://docs.gradle.org/current/userguide/organizing_gradle_projects.html#sec:build_sources) directory
