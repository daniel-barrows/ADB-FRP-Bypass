# ADB-FRP-Bypass
How to use [Android Debug Bridge](https://developer.android.com/tools/adb) (ADB) commands to bypass Android [Factory Reset Protection](https://www.samsung.com/ph/support/mobile-devices/what-is-device-protection-or-factory-reset-protection-frp/) (FRP).

1. Install ADB. ADP is part of [SDK Platform-Tools](https://developer.android.com/tools/releases/platform-tools), which is part of the [Android SDK](https://developer.android.com/tools). Installation options:
    1.   [Official download page](https://developer.android.com/tools/releases/platform-tools#downloads)
    2.   Fawaz Ahmed's [Latest ADB Fastboot and USB driver installer tool](https://github.com/fawazahmed0/Latest-adb-fastboot-installer-for-windows)
    3.   Corbin Davenport's [Nexus Tools](https://github.com/corbindavenport/nexus-tools).

2. Power on your device normally and connect it to your PC using USB cable.

3. Go the folder where the adb drivers are installed. (In most cases they are installed in the C Drive (Windows Drive))

4. Hold down Shift, right-click anywhere blank in the ADB folder, and select "Open command window here".

To remove FRP on **_Samsung devices_** via ADB commands: Type the following ADB FRP bypass command into the Command Prompt window one by one hitting Enter after each line.
```
adb shell am start -n com.google.android.gsf.login/
```
```
adb shell am start -n com.google.android.gsf.login.LoginActivity
```
```
adb shell content insert --uri content://settings/secure --bind name:s:user_setup_complete --bind value:s:1
```

To remove FRP on **_Other Brands / MTK /SPD_** via ADB commands: Type the following ADB FRP bypass command into the Command Prompt window and hit Enter after each line.
```
adb shell content insert --uri content://settings/secure --bind name:s:user_setup_complete --bind value:s:1
```



When the commands are all executed, the FRP lock will be removed from your device. That is how to use ADB FRP bypass to remove the lock from your phone.
