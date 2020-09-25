# Flutter engines (metal disabled)

These flutter engines have been compiled with metal disabled in iOS. This allows you to use SkSL cache files for iOS builds to reduce first-run jank.

## How to use

* Download the engine which matches your flutter version *exactly* - you must match your engine to your flutter sdk.
* Unzip the engine zips and move the `Flutter.framework` folder inside the zip into the respective folder at `$FLUTTER_HOME/bin/cache/artifacts/engine/[ios-profile/ios-release]` where `FLUTTER_HOME` represents where your flutter SDK lives on your disk. You should overwrite the existing `Flutter.framework` folder with the one contained in the zip file.
* Do a `flutter clean` and rebuild your project and it will now build iOS with metal disabled.
