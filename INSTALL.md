# How to setup an build the ConnectSDK.framework

## Initial
    git clone https://github.com/kdgm/Connect-SDK-iOS-Lite
    cd Connect-SDK-iOS-Lite
    git submodule update --init
    open ConnectSDK.xcodeproj

## XCode
* "File -> Project Settings" and change "Derived Data" to "Project-Relative Location"
* "File -> Add Files to ConnectSDK", and select the "modules" folder
* In project delete "GoogleCastTests" in "google-cast" folder.
* "Build Phases -> Headers", move the headers from private to public

## GoogleCast.framework

    curl -o modules/google-cast/GoogleCastSDK.zip https://developers.google.com/cast/downloads/GoogleCastSDK-2.7.1-Release-ios-default.zip
    unzip modules/google-cast/GoogleCastSDK.zip 'GoogleCastSDK-2.7.1-Release/GoogleCast.framework/*' -d modules/google-cast

## Xcode
* "Build Phases -> Link Binary With Libraries", add the "GoogleCast.framework"
* Select "Framework" as target and "Generic iOS Device", hit the run button
