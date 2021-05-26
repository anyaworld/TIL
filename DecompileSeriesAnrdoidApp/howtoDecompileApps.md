# README.md

## How to decompile apks [Link](https://codechacha.com/ko/how-to-decompile-android-apk/)

1. $ adb shell dumpsys package p > package_info.txt

1. $ adb pull "CodePath"

* adb pull /data/app/com.skillshare.Skillshare-iUURhkcFuQFdkbLcNFeYZA==

1. $ chmod 755 "PackageName"

* chmod 755 "com.skillshare.Skillshare-iUURhkcFuQFdkbLcNFeYZA=="

1. $ cd "PackageName"

1. $ apktool d -s -o decompiled base.apk

1. $ brew install jadx // install jadx // skip!!

1. $ jadx -h

1. jadx -d "decompiledoutputFoldername" "decompilefilename.apk"

1. dex2jar "filename.dex"

## apktool documents [from](https://codechacha.com/ko/how-to-decompile-android-apk/)

## jadx documents [from](https://codechacha.com/ko/how-to-decompile-android-apk/)

## download dex2jar [Link](https://github.com/pxb1988/dex2jar/releases)

## contents of package_info.txt

  Package [com.skillshare.Skillshare] (a9ea221):
    userId=10291
    pkg=Package{1774646 com.skillshare.Skillshare}
    codePath=/data/app/com.skillshare.Skillshare-iUURhkcFuQFdkbLcNFeYZA==
    resourcePath=/data/app/com.skillshare.Skillshare-iUURhkcFuQFdkbLcNFeYZA==
    legacyNativeLibraryDir=/data/app/com.skillshare.Skillshare-iUURhkcFuQFdkbLcNFeYZA==/lib
    primaryCpuAbi=arm64-v8a
    secondaryCpuAbi=null
    versionCode=5759 minSdk=21 targetSdk=30
    versionName=5.3.13
    splits=[base]
    apkSigningVersion=2
    applicationInfo=ApplicationInfo{7567007 com.skillshare.Skillshare}
    flags=[ HAS_CODE ALLOW_CLEAR_USER_DATA LARGE_HEAP ]
    privateFlags=[ PRIVATE_FLAG_ACTIVITIES_RESIZE_MODE_RESIZEABLE_VIA_SDK_VERSION HAS_DOMAIN_URLS PARTIALLY_DIRECT_BOOT_AWARE ]
    dataDir=/data/user/0/com.skillshare.Skillshare
    supportsScreens=[small, medium, large, xlarge, resizeable, anyDensity]
    usesOptionalLibraries:
      android.test.mock
    usesLibraryFiles:
      /system/framework/android.test.mock.jar
    timeStamp=2020-12-01 08:33:25
    firstInstallTime=2020-12-01 08:33:26
    lastUpdateTime=2020-12-01 08:33:26
    installerPackageName=com.android.vending
    signatures=PackageSignatures{25a0534 version:2, signatures:[b28e2721], past signatures:[]}
    installPermissionsFixed=true
    pkgFlags=[ HAS_CODE ALLOW_CLEAR_USER_DATA LARGE_HEAP ]
    install permissions:
      android.permission.DOWNLOAD_WITHOUT_NOTIFICATION: granted=true
      com.google.android.finsky.permission.BIND_GET_INSTALL_REFERRER_SERVICE: granted=true
      com.google.android.c2dm.permission.RECEIVE: granted=true
      android.permission.FOREGROUND_SERVICE: granted=true
      android.permission.RECEIVE_BOOT_COMPLETED: granted=true
      android.permission.BLUETOOTH: granted=true
      android.permission.INTERNET: granted=true
      com.android.vending.BILLING: granted=true
      android.permission.ACCESS_NETWORK_STATE: granted=true
      android.permission.ACCESS_WIFI_STATE: granted=true
      android.permission.WAKE_LOCK: granted=true
    User 0: ceDataInode=1316056 installed=true hidden=false suspended=false stopped=false notLaunched=false enabled=0 instant=false virtual=false
      lastDisabledCaller: com.android.vending
      gids=[3002, 3003]
