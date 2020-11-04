# Flutter engines (metal disabled)

These flutter engines have been compiled with metal disabled in iOS. This allows you to use SkSL cache files for iOS builds to reduce first-run jank.

How to use SkSL caching: https://flutter.dev/docs/perf/rendering/shader

## How to use

* Download the engine artifacts from this repository which matches your flutter version *exactly*. The version number of the folders here are the exact flutter tag you should checkout. Example:
```
cd $FLUTTER_HOME
git checkout tags/1.20.4
flutter doctor
flutter precache # Make sure you do this or else you might accidentally overwrite your metal-disabled engine later
```
* Unzip the engine zips and move the `Flutter.framework` folder inside the zip into the respective folder at `$FLUTTER_HOME/bin/cache/artifacts/engine/[ios-profile/ios-release]` where `FLUTTER_HOME` represents where your flutter SDK lives on your disk. You should overwrite the existing `Flutter.framework` folder with the one contained in the zip file.
* Do a `flutter clean` and rebuild your project and it will now build iOS with metal disabled.

Note: If you change your flutter channel it will download the engine artifacts again and overwrite the ones you just manually unzipped, so keep that in mind if you are switching channels often.

## Restoring the default engine

If you ever want to go back to the normal one, simply delete the engine artifacts and re-download them:
```
rm -rf $FLUTTER_HOME/bin/cache/artifacts/engine/*
flutter channel [stable|beta|dev|master]
flutter upgrade
flutter doctor
flutter precache
```

## Requesting new flutter versions

Please submit an issue if you want additional flutter versions supported.
