Content description bug
=======================

This project is a sample app to reproduce a bug with the `android:contentDescription` attribute.

Pre-requisite: have talkback enabled:
* Install the [Android Accessibility Suite](https://play.google.com/store/apps/details?id=com.google.android.marvin.talkback&hl=en) app from the Play Store.
* In the system settings, enable TalkBack

Steps to reproduce the bug:
* Build this app: `./gradlew assembleDebug`
* Install the app: `adb install app/build/outputs/apk/debug/app-debug.apk`
* Launch the app
* Tap anywhere except on the robot image
  - :white_check_mark: TalkBack reads "surface view label": OK
* Tap on the robot image:
  - Expected behavior: TalkBack reads "robot"
  - :x: Actual behavior: TalkBack briefly selects the robot image, then unselects the robot image, selects the surface view image, and reads "surface view label"
* Swipe left or right to select accessible elements.
  - :white_check_mark: Talkback can select the robot image and read "robot": OK


