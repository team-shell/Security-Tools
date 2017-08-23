# Security-Tools
A repo containing some useful security tools.

## Server
### Check Certificate
In the snippet below from a command line, the openssl tool's s_client command looks at Wikipedia's server certificate information. It specifies port 443 because that is the default for HTTPS. The command sends the output of openssl s_client to openssl x509, which formats information about certificates according to the X.509 standard. Specifically, the command asks for the subject, which contains the server name information, and the issuer, which identifies the CA.
`openssl s_client -connect wikipedia.org:443 | openssl x509 -noout -subject -issuer`

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
* `su` - login as root on the device (once you `adb shell` beforehandadd )
* `chmod -R 777 /data/data/com.facebook.orca`- apply root permissions to the app data directory
* `adb pull /data/data/com.facebook.orca/` - pull app data from the device

* `adb backup -noapk com.google.android.youtube` - backup app data from a device
* `dd if=backup.ab bs=24 skip=1 | python -c "import zlib,sys;sys.stdout.write(zlib.decompress(sys.stdin.read()))" > backup.tar` - uncompress the Android Backup Format into .tar format

### APK Unpack/Uncompress
You can use apktool to unpack and uncompress the files. 
* `apktool d base.apk`
* `unzip base.apk` - this will unzip a .apk file. With this tool you can see the META-INF folder

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
