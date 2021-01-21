# unity-swiftui-example

This repository demonstrates how to integrate Unity 2020.2.1f1 into
a Swift iOS app based on SwiftUI and built with XCode 12.

This repository is heavily based on the example published by Unity Technologies
available [here](https://github.com/Unity-Technologies/uaal-example/blob/master/docs/ios.md).

## Features

* Unity integration into SwiftUI
* Communication from Unity to native code
* Communication from native code to Unity **without** `SendMessage()`

The last point will allow you to transfer heavy data
without the need to serialize it to a string beforehand.

## Build

> Note: I have only tested the build with Unity 2020.2.1f1 and XCode 12.0

### Unity Project

Start first by opening the unity project and building it. As a build folder,
please build into `unityapp/Build/iOS/`.

### XCode Project

Open the workspace `unitysandbox.xcworkspace` at the root of this repository.
You can then build the sandbox app and run it in XCode.

## How

For a complete explanation of the architecture of this example, please have a
look at my [blog post (not yet available)]().

TODO:
* Having a LaunchScreen is mandatory for Unity to work

## FAQ

#### Unity doesn't render to my app

Between the moment you create the `UnityFramework` instance, and the moment you
can display it, it seems like there is an issue. Some people try to add a delay,
but this is definitely a hack.

In this example, it is assumed that whenever the API script starts, the Unity
window should be ready to be shown. This is achieved by sending a first message
from Unity to the native code. Whether this will work in every cases or not
is questionable, but for now it has done a good job for me.
