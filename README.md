# Security-Tools
A repo containing some useful security tools.

## Server
### OpenSSL
In the snippet below from a command line, the openssl tool's s_client command looks at Wikipedia's server certificate information. It specifies port 443 because that is the default for HTTPS. The command sends the output of openssl s_client to openssl x509, which formats information about certificates according to the X.509 standard. Specifically, the command asks for the subject, which contains the server name information, and the issuer, which identifies the CA.

* `openssl s_client -connect wikipedia.org:443 | openssl x509 -noout -subject -issuer`

Get the public key of the certificate from a host:
* `openssl s_client -connect google.com:443 | openssl x509 -pubkey -noout`

You can get the SHA-256 pin for a public key by going to - https://www.ssllabs.com/ssltest/index.html or by using:

`openssl s_client -servername www.example.com -connect www.example.com:443 | openssl x509 -pubkey -noout | openssl pkey -pubin -outform der | openssl dgst -sha256 -binary | openssl enc -base64`

Check certificate chain:

* `openssl s_client -connect wikipedia.com:443`


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
* `ps` - view running processes on the device with user id's
* `cat /data/system/packages.xml` - view the permissions of all apps on the device
* `cat /etc/permissions/platform.xml` - view the permission-to-group mappings (These are used to determine supplemental group IDs to set for the application)
* `pm install or adb install` - install an app on the device


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
