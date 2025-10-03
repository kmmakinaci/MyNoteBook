# Anroid ADB commands

* adb devices
* adb shell
* adb install MyApp.apk         -> install application using adb
        * adb install ~/Downloads/Full\ system\ info_v2.8.7_apkpure.com.apk
* adb pull /data/somefile       -> pull some file to your pc
* adb push somefile /data       -> psuh some file to android device
* adb reboot revoery            -> erase user partition, similar to factory reset
* adb shell pm list packages .f -> application package list
* adb shell pm list users       -> user list
* adb shell pm list features    -> Android feature list
* adb shell dumpsys display     -> Dump display device information
* adb shell dumpsys activity broadcasts -> See all boradcast messages
* adb shell lshal               -> List running HAL services (HIDLs)
* adb pull /data/tombstone/ .   -> Get application crash logs
* adb logcat *:E                -> Display all messages with error loglevel


