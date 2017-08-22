# Security-Tools
A repo containing some useful security tools.

## Mobile
### Pentesting Tools
* [MobSF/Mobile-Security-Framework-MobSF](https://github.com/MobSF/Mobile-Security-Framework-MobSF)
* [cSploit/android](https://github.com/cSploit/android)

### Deliberately Vulnerable Applications
* [OWASP/igoat](https://github.com/owasp/igoat)

### Android Debug Bridge
* `adb devices` - list of devices attached
* `adb shell pm list packages -f` - lists all installed apps and their locations
* `adb pull /data/app/com.google.android.youtube-1/base.apk` - pull one of those apps from the phone
* `adb shell service list` - list of system services

### APK Unpack/Uncompress
You can use apktool to unpack and uncompress the files. 
* `apktool d base.apk`

### Finding User ID
* `id` - find the current users id

### APK Decompilers
* [google/android-classyshark](https://github.com/google/android-classyshark)

### Android Deobfuscators
* [CalebFenton / simplify](https://github.com/CalebFenton/simplify)

### Cordova Secure Storage
* [pradeep1991singh / cordova-plugin-secure-key-store](https://github.com/pradeep1991singh/cordova-plugin-secure-key-store)
* [Crypho/cordova-plugin-secure-storage](https://github.com/Crypho/cordova-plugin-secure-storage)

## OWASP
### XSS Protection
* [ESAPI/node-esapi](https://github.com/ESAPI/node-esapi)
* [ecto/bleach](https://github.com/ecto/bleach)
