# PhysX 4.1 (Special Version for Games)

## How to compile for Windows & Android
1. Download Android NDK from here [NDK R11C Win64](https://dl.google.com/android/repository/android-ndk-r11c-windows-x86_64.zip), unpack and place it in the root folder
2. Run **generate_projects.bat** and choose a cross-compilation platform (I already added them in)
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

## PhysX 5 Now Available

The NVIDIA PhysX SDK version 5 is now available [here](https://github.com/NVIDIA-Omniverse/PhysX).
This repository will continue to be available to support legacy users.  We encourage all new projects to start on the new release.

## Introduction

Welcome to the NVIDIA PhysX SDK source code repository. This depot includes the PhysX SDK and the Kapla Demo application.

The NVIDIA PhysX SDK is a scalable multi-platform physics solution supporting a wide range of devices, from smartphones to high-end multicore CPUs and GPUs. PhysX is already integrated into some of the most popular game engines, including Unreal Engine, and Unity3D. [PhysX SDK on developer.nvidia.com](https://developer.nvidia.com/physx-sdk).

## Documentation

Please see [Release Notes](http://gameworksdocs.nvidia.com/PhysX/4.1/release_notes.html) for updates pertaining to the latest version.

The full set of documentation can also be found in the repository under physx/documentation or online at http://gameworksdocs.nvidia.com/simulation.html 

Platform specific information can be found here:
* [Microsoft Windows](http://gameworksdocs.nvidia.com/PhysX/4.1/documentation/platformreadme/windows/readme_windows.html)
* [Linux](http://gameworksdocs.nvidia.com/PhysX/4.1/documentation/platformreadme/linux/readme_linux.html)
* [Google Android ARM](http://gameworksdocs.nvidia.com/PhysX/4.1/documentation/platformreadme/android/readme_android.html)
* [Apple macOS](http://gameworksdocs.nvidia.com/PhysX/4.1/documentation/platformreadme/mac/readme_mac.html)
* [Apple iOS](http://gameworksdocs.nvidia.com/PhysX/4.1/documentation/platformreadme/ios/readme_ios.html)
 

## Quick Start Instructions

Requirements:
* Python 2.7.6 or later
* CMake 3.12 or later

To begin, clone this repository onto your local drive.  Then change directory to physx/, run ./generate_projects.[bat|sh] and follow on-screen prompts.  This will let you select a platform specific solution to build.  You can then open the generated solution file with your IDE and kick off one or more configuration builds.

To build and run the Kapla Demo see [kaplademo/README.md](kaplademo/README.md).
