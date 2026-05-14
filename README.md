# PhysX 4.1 For Games
## Introduction
A special version of PhysX 4, supporting the v143 toolset (Visual Studio 2022) and static library compilation.

This is achieved via deep modification to the CMake scripts, CMake toolchain files, and Python build scripts.

Tested on **Win64** and **Android** environments.

## Compile to Windows & Android
1. Download Android NDK from here [NDK R11C Win64](https://dl.google.com/android/repository/android-ndk-r11c-windows-x86_64.zip), unpack and place it in the root folder
2. Run **generate_projects.bat** and choose a cross-compilation platform (I have already added them in)
3. Go to **physx\compiler**, run cmake **--build ./SOLUTION_FOLDER_NAME**, for instance:
   > cmake --build ./OnlyStatic-vc17win64 --config checked --clean-first -j 20
   > 
   > cmake --build ./OnlyStatic-vc17win64 --config release --clean-first -j 20
   > 
   > cmake --build ./OnlyStatic-android-arm64-v8a-checked --clean-first -j 20
   >
   > cmake --build ./OnlyStatic-android-arm64-v8a-release --clean-first -j 20
4. Strip debug info to reduce the package size, for instance:
   > strip -g libPhysX_static.a
   >
   > (Location: android-ndk-r11c\toolchains\aarch64-linux-android-4.9\prebuilt\windows-x86_64\aarch64-linux-android\strip.exe)
5. Find the static libraries in **physx\bin**
