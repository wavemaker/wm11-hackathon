---
title:  How to build apk or ipa?
layout: default
parent: How To
nav_exclude: true
---

# {{ AppChef }}

AppChef builds app installers including APK and IPA from a ReactNative zip or Cordova zip of the application that can be exported from the WaveMaker Studio. Thus, generated APK or IPA, can be used for testing or can be uploaded to the Play Store and App Store for distribution. 

## Prerequisite to build using AppChef

To perform a Build using AppChef, you should have the application React Native zip.
WaveMaker provides an option to export your mobile application to a React Native. For more information, see [download cordova zip](/learn/hybrid-mobile/mobile-build-manual#how-to-export-cordova-zip).

Navigate to the appchef application using the below url

https://www.wavemakeronline.com/AppChef

To login, click **Login with WaveMaker**

![mobile-build-appchef-login-screen](/learn/assets/mobile-build-appchef-login-screen.png)

After successful login, to enable building a react native app, execute the following url in the address bar

https://www.wavemakeronline.com/AppChef/#/Main?enableReactNative=true

A option with **Create React Native build** will be shown beside Create New Build.

#Screenshot

## Steps to build using AppChef

Build through AppChef is a three-step process, as described below.
1. Upload React Native zip
2. Configure AppInfo
3. Configure Build

### Upload React Native zip

Click on create React Native build option, drag and drop or browse your files to upload cordova zip.

![mobile-build-appchef-upload-cordova-zip](/learn/assets/mobile-build-appchef-upload-cordova-zip.png)

### Configure AppInfo

1. After Successful upload, AppInfo will be pre-populated from your uploaded react native zip. You have options to modify them to your choice.

2. Click Next to configure the Build options.

![mobile-build-appchef-appInfo](/learn/assets/mobile-build-appchef-appInfo.png)

### Configure Build

In this step, you can provide a distribution profile and choose certificates of the profile respectively.

Refer the following [steps](https://docs.wavemaker.com/learn/hybrid-mobile/mobile-build-appchef#configure-build)

### About AppChef

To Manage or secure certificates, Refer [here](https://docs.wavemaker.com/learn/hybrid-mobile/mobile-build-appchef#manage-or-upload-certificates)

To check the status of submitted build request or to manage the existing app, Refer [here](https://docs.wavemaker.com/learn/hybrid-mobile/mobile-build-appchef#checking-status-of-the-submitted-build-request)











