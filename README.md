# Android-cert-Install-
Android Cert install 


Create Certificate
1 - Export Burp certificate to .DER e.g cacert.der
2 - openssl x509 -inform DER -in cacert.der -out cacert.pem
3 - openssl x509 -inform PEM -subject_hash_old -in cacert.pem |head -1
4 - mv cacert.pem {hash}.0

Setup Certificate
1 - adb root
2 - adb remount
3 - adb push {cert}.0 /sdcard/
4 - adb shell
5 - mv /sdcard/{cert}.0 /system/etc/security/cacerts/
6 - chmod 644 /system/etc/security/cacerts/{cert}.0
7 - reboot
