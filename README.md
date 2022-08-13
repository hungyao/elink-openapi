# LinkJapan eLife OpenAPI

This repo explains how to access the API used smarthome devices that connect to the LinkJapan eLink ecosystem.  Normally, these devices can only be controlled using a voice assistant or via the vendor's [HomeLink](https://play.google.com/store/apps/details?id=jp.co.linkjapan.elife&hl=en&gl=US) app (also available for iOS).

However, through some careful examination of the vendor's software, we can figure out how the API works. Unfortunately, this doesn't yet let you run these devices without using the vendor's cloud services (e.g., completely disconnected from the internet) - that's something that I'd like to figure out in the future.  Rather, we're just mimicking the API calls made by the app itself.

This repository and its maintainers are not affiliated with LinkJapan, etc.  This repository and its maintainers give no warranty and accept no responsibility or liability for the accuracy or the completeness of the information and materials contained in the repository.

## Devices tested

- [Iris Ohyama SMT-PL1 Smart Plug](https://amzn.to/3JSZnDR)
- [Iris Ohyama SMT-RC1 Smart Remote Control](https://amzn.to/3AkdT4D)

## API

[LinkJapan eLife OpenAPI documentation](https://hungyao.github.io/elink-openapi)

## Examining the code

To proceed here, you need to obtain the APK somehow (either from your Android device, or from some APK mirroring service).  Once you do, proceed with the steps below:

```
# Extract class files to be read with a Java class decompiler.
d2j-dex2jar -f path_to_homelink.apk
# Then open the resulting jar with https://github.com/java-decompiler/jd-gui

# Extract the react native code.
apktool d path_to_homelink.apk
npx react-native-decompiler -i path_to_homelink_apk/assets/index.android.bundle -o ./output
```
