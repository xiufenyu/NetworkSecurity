|Command	    | Description   |
| ------------- | ------------- |
$ adb shell     |               |	
|$ ctrl + D	    |Exit shell     |
|$ adb devices	|List devices on the computer|
|$ adb connect <IP:Port>	| Connect to the device|
|$ adb push <host_path>  <phone_path>	| Upload file from the host to Android phone|
|$ adb pull <phone_path>  <host_path>	|Download file from Android phone to the host|
|$ adb shell pm list packages -f	    ||
|$ adb shell pm list packages -f -3||
|$ adb shell pm path com.security.xvpn.z35kb	| List the path of split apks|
|$ adb install-multiple apk1  apk2  apk3 ||
|$ adb install com.imo.android.imoim	||
|$ adb uninstall com.imo.android.imoim||
|$ adb kill-server	||
|$ adb start-server||
|$ ps -e \| grep frida ||	
|$ kill -9 <pid> ||
|$ logcat -v color 2>&1 \| tee logs.txt	| Print Debug log|
|$ logcat *:D -v color 2>&1 \| tee logs.txt	||
|$ logcat -c |	Clear log
