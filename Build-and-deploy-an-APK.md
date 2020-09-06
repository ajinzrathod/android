[Source](https://developer.android.com/studio/build/building-cmdline)


## Build a debug APK
* For immediate app testing and debugging, you can build a debug APK.  The debug APK is signed with a debug key provided by the SDK tools and allows debugging through adb

* To build a debug APK, open a command line and navigate to the `~/AndroidStudioProjects/"project_name"/`. To initiate a debug build, invoke the `assembleDebug` task:

> ./gradlew assembleDebug

This creates an APK named `module_name-debug.apk` in `~/AndroidStudioProjects/"project_name"/"module_name(app)"/build/outputs/apk/debug/`. The file is already signed with the debug key and aligned with zipalign, so you can immediately install it on a device.

Or to build the APK and immediately install it on a running emulator or connected device, instead invoke `installDebug`:

> ./gradlew installDebug

The "Debug" part in the above task names is just a camel-case version of the build variant name, so it can be replaced with whichever build type or variant you want to assemble or install. For example, if you have a "demo" product flavor, then you can build the debug version with the `assembleDemoDebug` task.

## If error occurs or Application is not shown in App Launcher

### If you are running the Application from **Android Development Studio** and it shows
```
Error while executing am start -n ....
...
Error while Launching activity
```

**OR**

### If the Application is not shown in App Launcher of your device.

* The error occurs when you delete the app when you are still testing it on your phone. The app shows as deleted because it disappears from your launcher, To fully delete the app follow the steps below.

* It worked perfectly after clicking on settings => `Apps & notification` => `App info` => " **find the name of the app**" => "on top right corner **click on the three dots**"" => `Uninstall for all users`

* [Source] (https://stackoverflow.com/questions/35330756/android-application-error-while-running-the-application/41646204)
