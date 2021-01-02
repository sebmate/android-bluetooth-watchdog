# android-bluetooth-watchdog

**Problem:** It seems that on some Android smartphones the whole Bluetooth stack crashes randomly. This can cause Corona warning apps (e.g. Corona Contact Tracing Germany) to stop working randomly. 

**Solution:** Interestingly, in such an error case, the smartphone will no longer find any other Bluetooth devices. According to my observations, it helps to briefly turn Bluetooth off and on again in the system settings. In this repository I provide an "Automate" script that monitors the basic Bluetooth functionality of the Android system and automates the toggling of Bluetooth.

**How it works:** The script permanently performs Bluetooth scans. If no other Bluetooth devices are found, Bluetooth is briefly disabled and then re-enabled. According to my tests, this helps the app "Corona Contact Tracing Germany" to continue working properly. (Note: In case there really are no other Bluetooth devices around, the toggling is not a problem, because then nothing can get "traced" or interrupted either). If Bluetooth can't be established with this, the script runs into an exception where the phone vibrates every 10 minutes. In this case you should restart the phone. 

**Installation:** The .flo file can be imported into the Android app "Automate" (see: https://llamalab.com/automate/). This app seems to be free of ads and trackers. If you are not using the Google ecosystem, you can also install the app via the Aurora Store (see: http://auroraoss.com/). Then just import the .flo file and rename it, e.g. to "BT Watchdog" and run the script. You can also configure "Automate" so that the script is already started at boot time. 

Note: It may happen that the script runs into an exception at startup and the phone vibrates first because Bluetooth is not immediately available. This is OK.

![Flow](https://github.com/sebmate/android-bluetooth-watchdog/blob/main/BT%20Watchdog.png)

